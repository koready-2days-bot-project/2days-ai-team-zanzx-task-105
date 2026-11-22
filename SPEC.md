# Design handoff spec · Address-to-rider connected flow · v1

> For designers · Fill this in and link it when you hand off to the developer.

**Figma file:** Screens: see the HTML design (not Figma)
**Final page:** `Final` — only this page is the version to build

## Screens

| # | Screen | Language | Frame name | Priority |
| --- | --- | --- | --- | --- |
| 1 | Address Search | English | `01 Address Search / Default` | Must |
| 2 | Address Details | English | `02 Address Details / Default` | Must |
| 3 | Checkout & Requests | English | `03 Checkout / Default` | Must |
| 4 | Order Confirmation | English | `04 Order Placed / Default` | Must |
| 5 | Rider Order Detail | Korean | `05 Rider View / Default` | Must |

## English input → Korean display

| Customer enters (English screen) | Field name (Data Guide) | Rider sees (Korean screen) | Notes |
| --- | --- | --- | --- |
| 10, Donggyo-ro 51-gil, Mapo-gu | `road_address_en` → `road_address_ko` | 서울특별시 마포구 동교로51길 10 | Bold 16px header on rider card |
| Hanbit Village Complex 2 Apt. Bldg 101 Rm 402 | `building_name_en` + unit | 한빛마을2단지아파트 101동 402호 | Detailed line 15px bold, original English string underneath (12px italic) |
| Leave at door and ring doorbell | `rider_request_en` → preset translation | 문 앞에 두고 벨을 눌러주세요 | Highlighted blue box (#EFF6FF), original English preset caption below |
| Custom untranslatable text | `rider_request_en` (fallback) | Please call me when you reach the gate | Warning box (#FFFBEB), fallback tag shown |

## States per screen

| Screen | Default | Empty | Error | Other (loading, no results) |
| --- | --- | --- | --- |
| Address Search | Input active with recent search cards | Empty input field | Invalid input error state | No matching address found message |
| Address Details | Pre-filled address with room input | Room input empty state | Unit missing validation error | - |
| Checkout | Cart summary with translated request dropdown | - | Required field missing error | Processing order loading overlay |
| Order Confirmation | Success message with rider preview card | - | - | - |
| Rider Order Detail | Full delivery details in Korean with original English text | - | Delivery issue report state | Translation failed state (rider sees customer's original English text) |

## Specs

- **Spacing:** 4px / 8px / 12px / 16px / 24px / 32px
- **Colors:** Primary Text (`#111827`), Background (`#F3F4F6`), Card (`#FFFFFF`), Primary Green (`#00805A`), Rider Highlight (`#EFF6FF`), Error (`#DC2626`), Warning Amber (`#D97706`)
- **Type:** System Sans-Serif; Header 20px Bold, Section Title 16px Bold, Body 14px Regular, Caption/Original 12px Italic
- **Components:** Button (Primary Green `#00805A`, Secondary Gray `#F3F4F6`), Input Field (Default, Error), Card, Rider Card, Translation Badge
- **Mobile frame size:** 390 × 844

## Assets

- Export: Action icons as inline SVG
- Where: Included in index.html codebase

## Open decisions

- [none]

## Changes since the last version

- Final handoff: Added translation failed state for rider order detail screen where rider sees customer's original text.