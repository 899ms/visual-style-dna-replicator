# Behavioral Validation Scenarios

## Baseline failure captured before authoring

Prompt: turn a childlike deer IP into its grown-up version using slender adult poster references.

Observed no-skill failure: the agent described the result as “normal 6.8-head adulthood” but recommended legs occupying 53–56% of total height. This still biases the result toward fashion-model elongation and conflicts with natural growth.

Expected behavior with this Skill:

- Preserve identity anchors.
- Treat growth as skeleton reconstruction, not scaling.
- Keep pelvis near the vertical midpoint.
- Keep crotch-to-sole length around 47–50% unless the user explicitly requests exaggerated fashion anatomy.
- Create a 35–45° pose through torso/pelvis rotation and weight distribution, not leg stretching.

## Additional acceptance scenarios

1. Three landmark posters are analyzed into shared ink, paper, palette, spacing, illustration and typography rules; landmark identity remains variable.
2. A child photography poster series is converted into a shared color/layout/doodle system while the child, prop and copy remain replaceable.
3. A car typography poster keeps giant condensed type and diagonal motion geometry when the subject changes to a laptop or air conditioner.
4. A silhouette festival poster keeps translucent backlight, cool haze, yellow accent and asymmetric editorial type when the subject changes.
5. A brand character poster preserves face, logo spelling and palette while changing only pose or age.
