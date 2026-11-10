# Dynamic Art Signature (动态艺术签名)

Input a name, one object and a gradient color; first merge the object's form into the letterforms, then produce two independent writing strokes. Read [the standalone module](../skills/dynamic-art-signature/SKILL.md) and its design and rendering references; do not reuse the sticker avatar light-motion treatment.

By default the two strokes are separate, about 1 second apart; the main stroke is fast and slows at the end as the tip tapers; no base stamp, no shake, no rebound. Handwritten feel means pressure modulation, stroke weight and sharp tips — not metal, chalk or 3D material by default.

[Nine samples](../examples/dynamic-signatures/README.md) · [Style entry](../styles/dynamic-signatures/STYLE.md)


Supports Chinese and English names. Chinese defaults to cursive and can switch to semi-cursive on request; both two- and three-character names must keep the complete name and a visible image motif. Three-character names keep the two-stroke writing rhythm while the layout and the final character's tip are redesigned. See [the Chinese rules](../skills/dynamic-art-signature/references/chinese.md).
