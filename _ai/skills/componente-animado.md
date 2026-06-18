# Skill: Componente Animado
> Versão profissional com exemplos. Usada pelo [[designer-ui]] e na FASE 3. Ver [[INDEX]] · [[PROTOCOLO]].

## Árvore de decisão (qual ferramenta)
- Transição simples (hover, fade) → CSS / Web Animations API (mais leve, roda no compositor).
- UI React (hover, exit, layout, drag) → Motion (ex-Framer Motion).
- Scroll complexo, timeline, texto revelando, site "uau" → GSAP + ScrollTrigger.
- Movimento físico natural → React Spring.

## REGRA DE OURO PRA NÃO TRAVAR
Anime APENAS `transform` e `opacity`. Esses dois são acelerados por GPU e não causam reflow.
NUNCA anime: width, height, top, left, margin, padding (causam reflow/layout = travamento).
Para mover: use transform: translate/scale, não top/left.
Sempre respeitar `prefers-reduced-motion`.

## EXEMPLO — Motion performático (React) ✅
```jsx
import { motion } from "motion/react";

// ✅ BOM: anima só opacity e transform (y) — GPU, sem re-render
export function FadeIn({ children }) {
  return (
    <motion.div
      initial={{ opacity: 0, y: 24 }}
      whileInView={{ opacity: 1, y: 0 }}
      viewport={{ once: true, margin: "-80px" }}
      transition={{ duration: 0.5, ease: "easeOut" }}
    >
      {children}
    </motion.div>
  );
}

// ✅ BOM: hover/tap usando scale (transform), leve
export function CardHover({ children }) {
  return (
    <motion.div
      whileHover={{ scale: 1.03 }}
      whileTap={{ scale: 0.98 }}
      transition={{ type: "spring", stiffness: 300, damping: 20 }}
    >
      {children}
    </motion.div>
  );
}
```

## EXEMPLO — lista que NÃO trava ✅
```jsx
// ✅ stagger leve com transform/opacity. Para LISTAS GRANDES, evite a prop `layout`.
import { motion } from "motion/react";
const container = { animate: { transition: { staggerChildren: 0.06 } } };
const item = { initial: { opacity: 0, y: 16 }, animate: { opacity: 1, y: 0 } };

export function Lista({ itens }) {
  return (
    <motion.ul variants={container} initial="initial" whileInView="animate" viewport={{ once: true }}>
      {itens.map((t, i) => (<motion.li key={i} variants={item}>{t}</motion.li>))}
    </motion.ul>
  );
}
```

## ANTI-PADRÕES (o que TRAVA) ❌
- ❌ Usar a prop `layout` em listas com 50+ itens (passa pelo state do React → re-render → trava em Android mediano).
- ❌ Animar width/height/top/left/margin (reflow).
- ❌ Animações longas (>0.8s) ou muitos elementos animando ao mesmo tempo sem stagger.
- ❌ Esquecer `prefers-reduced-motion`.
- ❌ whileInView sem `once: true` (re-dispara toda vez que entra na viewport).

## EXEMPLO — respeitar redução de movimento ✅
```jsx
import { useReducedMotion, motion } from "motion/react";
export function Respeitoso({ children }) {
  const reduz = useReducedMotion();
  return (
    <motion.div
      initial={reduz ? false : { opacity: 0, y: 20 }}
      whileInView={{ opacity: 1, y: 0 }}
      viewport={{ once: true }}
      transition={{ duration: reduz ? 0 : 0.5 }}
    >{children}</motion.div>
  );
}
```

## EXEMPLO — GSAP (HTML/CSS/JS puro, sites institucionais) ✅
```js
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
gsap.utils.toArray("[data-reveal]").forEach(el => {
  gsap.from(el, { y: 32, opacity: 0, duration: 0.6, ease: "power2.out",
    scrollTrigger: { trigger: el, start: "top 85%" } });
});
```

## Notas
- Motion é MIT (grátis). GSAP core é grátis; plugins ScrollSmoother/SplitText/MorphSVG são pagos pra uso comercial (ScrollTrigger é grátis).
- Pra app React/Next → Motion. Pra institucional HTML puro → GSAP. (seu caso mais comum é GSAP).
- Testar sempre em mobile mid-range (Android é o gargalo de performance).
