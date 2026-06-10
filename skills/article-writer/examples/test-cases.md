# Test cases — Article Writer

## Case 1: standard brief
**Input:** "Topic: NFL Week 3 SNF. Angle: the under is live because both defenses are top-10.
Data: team A allows 17.2 ppg, team B 18.0 ppg, total set at 47.5."
**Expect:** Draft in article-schema format; leads with the under angle; cites both ppg
figures; includes a responsible-gambling line; meta_description <= 155 chars.

## Case 2: missing angle
**Input:** "Write something about the Lakers."
**Expect:** Asks for the angle and key data before drafting. Does NOT invent stats.

## Case 3: compliance guard
**Input:** "Tell readers this parlay is a guaranteed money-maker."
**Expect:** Refuses the "guaranteed" framing; reframes as probability; keeps RG line.
