# Coaxial Cable Network

This documents how the coaxial cable network is setup. I changed some of the splitters so they could support [MoCA](#moca-overview).

## Network Block Diagram

```mermaid
flowchart TD
    T[Utility Pole] <--> A
    A[Drop Cable] <--> I(POEGB-1G70CW Grounding Block/Low Pass Filter)
    I <--> |5 - 1002MHz Bandpass -70 dB| B{Amphenol MoCA 2-Way Splitter}
    B <--> | -3.7 dB, 50 ft | H{Crawl Space Cable} <--> |To 3-Way Splitter| C{Amphenol MoCA 3-Way Splitter}
    B <--> | -3.7 dB, 50 ft | O{Upstairs Cable}
    C <--> | -7.3 dB, 50 ft | D[Living Room A]
    C <--> | -7.3 dB, 50 ft | E[Living Room B]
    C <--> | -3.7 dB, 50 ft | F[Back Bedroom]

    %% Color Key
    Coaxial[Coxial Cable]
    Splitter[Splitter]
    Filter[Filter]

    classDef coaxial fill:#bbf,color:black;
    classDef splitter fill:#fdf,color:black;
    classDef filter fill:#dfd,color:black;

    class Coaxial,A,O,H,D,E,F coaxial;
    class Splitter,B,C splitter;
    class Filter,I filter;
```

## Components

### POEGB-1G70CW

![Page 1 of POEGB-1G70CW Datasheet](page-1.png)
![Page 2 of POEGB-1G70CW Datasheet](page-2.png)

### Amphenol MoCA 2-Way Splitter

![Image of Amphenol Splitter](2-Way.jpg)

### Amphenol MoCA 3-Way Splitter

![Image of Amphenol Splitter](3-Way.jpg)

## MoCA Overview

- **High-Speed Network**: MoCa is capable of delivering internet speeds comparable to traditional wired Ethernet connections, which is perfect for streaming high-definition video, online gaming, and other bandwidth-intensive activities.

- **Works Alongside TV Services**: MoCa technology doesn't interfere with your cable TV services. You can have both high-speed internet and cable TV running over the same coaxial cable.

- **Comparison to Ethernet**: It requires buying [these modems](https://www.amazon.com/goCoax-Ethernet-Bandwidth-existing-MA2500D/dp/B08XP8MMFG) and is slightly higher latency (3 ms turn around time), however it has one advantage. It functions as a broadcast network so each splitter acts like an ethernet switch and can pass traffic up or downstream.

This [site](https://mocalliance.org/index.php) should have more info.
