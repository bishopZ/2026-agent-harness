# Pressure Test — One bus ride

**Status:** Approved (demo)

## Crux risks

| ID | Risk | Why it matters | Mitigation |
|---|---|---|---|
| R1 | Schedule data is too thin for a useful guide | Demo collapses into vague tourism copy | Stick to 801 endpoints and three named public stops; cite CapMetro public pages |
| R2 | Accidental private or partner content | Teaching repo must stay publishable | Public POIs only (Capitol, South Congress strip, Domain area) |
| R3 | Scope creeps into a full trip planner | Class loses the "bounded artifact" lesson | One ride, one page, no live API |

## Kill criteria

Drop if CapMetro stops publishing public route pages for 801, or if the guide needs non-public data to be honest.

## Experiments (demo-light)

- E1: Can a stranger follow boarding → three stops → alight using only the guide? (owner read-through)
- E2: Grep the folder for partner or private names; expect zero hits.

## Recommendation

Proceed. Risks are manageable for a teaching prop.
