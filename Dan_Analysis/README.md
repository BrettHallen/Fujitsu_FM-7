# Dan's Analysis – FM-7 / FM-NEW7 Revision Identification

Contributed by **Dan** ([@dan-and](https://github.com/dan-and)) in
[issue #1](https://github.com/BrettHallen/Fujitsu_FM-7/issues/1), October 2026.
Dan owns three FM-7 machines, each with a different mainboard revision. His photos
and notes are reproduced below.

## Summary

| | Board 1 | Board 2 | Board 3 |
| --- | --- | --- | --- |
| **Case sticker** | S13B-0600-B200 | S13B-0700-B7709 | S13B-0700-B770 |
| **Power switch** | Black | Beige | Grey |
| **Keycap front graphics** | No | No | Yes |
| **Case colour** | Beige | Slightly orange | Slightly orange |
| **Mainboard** | S320-0300-T054/04 (large) | S320-0400-T874/01 (smaller) | S320-0400-T874/02 |
| **Audio (AY-3-8910 PSG)** | Plug-in daughter board S320-0300-T102/02 | Integrated on mainboard | Integrated on mainboard |
| **Boot EPROM** | TL11-11 | TL11-11 | TL11-11 |
| **Character ROM** | TM11-12 (stickered) | TM11-13 | In MB83256 mask -167 combo ROM |
| **Sub-system monitor** | MB8364 | MB8364 | In MB83256 mask -167 combo ROM |
| **F-BASIC ROM** | MB83256 mask -107 = **F-BASIC V3.00** | MB83256 mask -128 = **F-BASIC V3.01** | MB83256 mask -160 = **F-BASIC V3.02** |
| **TK11-11 (16-pin, M139 address decoder)** | Present | Not fitted | – |
| **Date codes** | Mainboard 8242–8312, audio board 8242–8309, TM11-12 8305 | 8340–8416 | 8430–8445 |
| **Wire bridges / bodges** | Not yet recorded | Yes – a different set from Board 3 | Solder-side wires plus an IC-to-IC capacitor on the component side |

**Board 3 matches the FM-NEW7 being rebuilt in this repository** – same ROMs, same
bodge wires, and chips dated around 8503.

All three boards differ in IC placement, not just in which parts are fitted.

---

## Board 1 – early revision with audio daughter board

- Black power switch; keycaps lack the front graphics stickers.
- Case is a more neutral beige than later units, which tend slightly orange.
- Bottom sticker: **S13B-0600-B200**

![Board 1 – machine and bottom sticker](https://github.com/user-attachments/assets/2dc82490-323e-436c-b219-9fc1e1597dcc)

**Mainboard S320-0300-T054/04** (the large board) carries a piggyback daughter board,
**S320-0300-T102/02**, with the AY-3-8910 – the complete PSG/audio section as a
plug-in module.

ROMs:
- TL11-11 – boot EPROM
- TM11-12 – character ROM (stickered)
- MB8364 – sub-monitor
- TK11-11 – small 16-pin (2×8) part
- MB83256 mask -107 – F-BASIC V3.00

Date codes: audio daughter board 8242–8309, mainboard 8242–8312, TM11-12 8305.
Wire bridges on this board have not been recorded yet.

PCB with the audio daughter board fitted:

![Board 1 PCB with audio daughter board](https://github.com/user-attachments/assets/9fc84a04-563f-4ca3-95c3-4a869918ba1b)

Cleaned up:

![Board 1 PCB cleaned](https://github.com/user-attachments/assets/5beae55b-0d57-4703-9567-243309d7a1e5)

---

## Board 2 – audio integrated

- Beige power switch; keycaps still lack the front graphics stickers.
- Bottom sticker: **S13B-0700-B7709**

![Board 2 – machine and bottom sticker](https://github.com/user-attachments/assets/a005d5ad-9324-4c65-8709-7bb3b227f7ae)

**Mainboard S320-0400-T874/01** (the smaller board) with the audio section integrated.

ROMs:
- TL11-11 – boot EPROM
- TM11-13 – character ROM (re-checked and confirmed)
- MB8364 – sub-monitor (initially logged as MB8346, corrected)
- MB83256 mask -128 – F-BASIC V3.01
- No stickers on the chips, only Fujitsu part numbers.

There is **no TK chip** – every 16-pin IC was checked and all were TTL logic, so the
M139 address decoder was dropped on this revision.

Date codes 8340–8416, placing the board roughly 18 days before market launch.
Its wire bridges are a different set from Board 3.

![Board 2 PCB](https://github.com/user-attachments/assets/a56e422b-7b46-4349-a58f-338eccef3e5a)

---

## Board 3 – same revision as the FM-NEW7 in this repo

- Grey power switch; keycaps have the front graphics stickers.
- Rear sticker: **S13B-0700-B770**

![Board 3 – machine and sticker](https://github.com/user-attachments/assets/e952c997-972c-4a10-be42-5f316eba8cc7)

**Mainboard S320-0400-T874/02.**

ROMs:
- TL11-11 – boot EPROM
- MB83256 mask -160 – F-BASIC V3.02
- MB83256 mask -167 – combo ROM covering both the character generator and the
  sub-system monitor, so **no MB8364 is fitted**

Date codes 8430–8445.

The board has wire bridges on the solder side plus a capacitor soldered IC-to-IC on
the component side – identical to the FM-NEW7 machine in this repository, whose chips
date to around 8503 and whose ROMs also match Board 3 exactly. Dan didn't photograph
the component side, but reports it looks exactly like the board in Brett's video.

PCB rear side, showing the same bodge wires:

![Board 3 PCB rear with bodge wires](https://github.com/user-attachments/assets/809e221f-0528-4eb7-aca1-cc656aab88f6)
