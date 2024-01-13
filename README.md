# Coaxial Cable Network

This documents how the coaxial cable network is setup. I changed some of the splitters so they could support [MoCA](#moca-overview).

## Network Block Diagram

```mermaid
flowchart TD
    A[fa:fa-tv + fa:fa-globe Drop Cable] <--> I(POEGB-1G70CW Grouding Block/Low Pass Filter)
    I <-->|5 – 1002MHZ Bandpass -70 dB| B{Amphenol MoCA 2-Way Splitter}
    B <-->|-3.7 dB, 50 ft?| H{fa:fa-ghost Crawl Space Cable} <--> C{Amphenol MoCA 3-Way Splitter}
    B <-->|-3.7 dB, 50 ft?| O{fa:fa-computer Upstairs Cable}
    C <-->|-7.3 dB, 50 ft| D[Living Room A Outlet]
    C <-->|-7.3 dB, 50 ft| E[Living Room B]
    C <-->|-3.7 dB, 50 ft| F[Back fa:fa-bed Room]

    click I href "POEGB-1GCW, POEGB-1G70CW PPC MoCA POE 40-70dB Groundblock Specs_07102019.pdf" "Open Datasheet"
    click B href "2-Way.jpg"
    click C href "3-Way.jpg"
```

## MoCA Overview

- **High-Speed Network**: MoCa is capable of delivering internet speeds comparable to traditional wired Ethernet connections, which is perfect for streaming high-definition video, online gaming, and other bandwidth-intensive activities.

- **Works Alongside TV Services**: MoCa technology doesn't interfere with your cable TV services. You can have both high-speed internet and cable TV running over the same coaxial cable.

- **Comparison to Ethernet**: It requires buying [these modems](https://www.amazon.com/goCoax-Ethernet-Bandwidth-existing-MA2500D/dp/B08XP8MMFG) and is slightly higher latency (3 ms turn around time), however it has one advantage. It functions as a broadcast network so each splitter acts like an ethernet switch and can pass traffic up or downstream.

This [site](https://mocalliance.org/index.php) should have more info.
