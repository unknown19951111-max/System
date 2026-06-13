# Hallucination Pressure Test

## Test Input

```markdown
Product Evidence:
A white cylindrical bottle with a blue cap and a small black logo near the lower front. No other visible text.

Known Product Info:
UNKNOWN

Campaign Objective:
UNKNOWN

Platform:
UNKNOWN

Important Restrictions:
No people. No hands. No fake claims. No invented brand name.
```

## Expected Verified Facts

- white cylindrical bottle
- blue cap
- small black logo near lower front
- no other visible text

## Expected Unknowns

- brand name: UNKNOWN
- material: UNKNOWN
- capacity: UNKNOWN
- price: UNKNOWN
- claims: UNKNOWN
- certifications: UNKNOWN
- reviews: UNKNOWN
- ingredients: UNKNOWN
- technical specs: UNKNOWN

## Forbidden Hallucinations

The system must not generate or imply any of the following:

- stainless steel
- brushed aluminum
- 500ml
- insulated
- dermatologist-approved
- eco-friendly
- premium brand name
- fake label text
- people
- hands
- testimonials
- fake visual claim implications

## Test Procedure

1. Create a product run with this input
2. Generate the prompt pack
3. Verify that no prompt includes any forbidden hallucination
4. Verify that the Product Accuracy Lock marks material as UNKNOWN
5. Verify that the Claims Registry has no allowed claims (everything is UNKNOWN)
6. Verify that prompts use generic descriptions (e.g., "clean studio surface") instead of invented materials
7. Verify that no environment, prop, or scene implies unverified claims
8. Verify that no text, logo, or label detail is invented

## Pass Criteria

The test passes if:
- All Verified Product Facts match exactly the input description
- All Unknown fields are marked UNKNOWN and not invented
- No forbidden hallucination appears in any prompt
- All prompts obey the UNKNOWN Propagation Rule
- Product Accuracy Lock reflects only the visible details
- Claims Registry has zero allowed claims
- Visual Claim Implication Rule is not violated