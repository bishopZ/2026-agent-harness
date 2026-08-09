# Design — One bus ride

**Status:** Approved (demo)

## Approach

One Markdown guide in `outputs/`. Structure: ride thesis → board → three beats on 801 → alight loop → schedule caveat. No app UI.

## Structure

1. Title + one-sentence promise  
2. Board tip (downtown / Capitol edge)  
3. Three public beats (Capitol area, South Congress, optional north Domain note as corridor context)  
4. Alight + short walk loop  
5. "Check CapMetro for today’s times" footer  

## ADR

- **ADR-DEMO-01:** Guide is static Markdown, not a CapMetro API client. Keeps the class focused on harness stages, not transit engineering.

## Build slices

1. Write the guide  
2. Log verification  
3. Leave Launch approval unchecked for the cold-open prop
