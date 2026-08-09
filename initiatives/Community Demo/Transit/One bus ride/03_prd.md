# PRD — One bus ride

**Status:** Approved (demo)  
**deliverable_class:** document

## Goal

Ship `outputs/one-bus-ride-guide.md`: one page, MetroRapid 801, public data only.

## Requirements

| ID | Requirement |
|---|---|
| FR-1 | Name the route (801) and the ride shape (board → stops → alight) |
| FR-2 | List three public points of interest a rider can actually visit |
| FR-3 | Tell the reader to verify today’s times on CapMetro’s public site |
| FR-4 | Zero private, partner, or confidential content |

## Acceptance criteria

| AC | Criterion |
|---|---|
| AC-01 | Guide is one page or less when printed/previewed |
| AC-02 | Mentions MetroRapid 801 explicitly |
| AC-03 | Includes ≥3 public POIs |
| AC-04 | Keyword scan finds no partner or private initiative names |

## Non-goals

Live GTFS integration, tickets, notifications, multi-route itineraries.

## Verification

Read-aloud of the guide; grep for forbidden names; confirm CapMetro is cited as the schedule source.
