---
title: Project Verison 2.0
---
## Overview

If Team 307 were to develop a second version of this project, the most important improvement would be the temperature sensing subsystem. In the current design, the sequence diagram labels this subsystem as “Not Applicable” because it was not functional by the time of the innovation showcase. However, several improvements could ensure it becomes fully operational in the next version.

One major improvement is adjusting component footprint sizing. In the original design, very small surface-mount components—such as the PIC18(LF)47K42 Microcontroller and the TMP1075DGK temperature sensor—made soldering difficult and time-consuming. Selecting larger footprint components, when possible, would simplify assembly and significantly reduce soldering errors and build time.

Another key improvement is adding test points to the PGC and PGD pins for the MPLAB Snap debugger, along with ensuring a proper MCLR pull-up connection. During development, attempts to program the microcontroller in MPLAB frequently resulted in a “PGC error.” This issue was likely related to the MCLR connection or debugging interface, even though configuration bits were correctly set. Since MPLAB does not always clearly identify the root cause of such errors, adding dedicated test points would allow for quicker debugging and more efficient troubleshooting, rather than relying on repeated trial and error.

By implementing these improvements, the temperature sensing subsystem would be far more likely to function properly. This would allow the team to move beyond basic hardware issues and focus on higher-level features, such as implementing a communication protocol, instead of having the subsystem remain “Not Applicable.”

In addition to that, Team 307 would implement the usage of ribbon cables as it was hard to navigate through the wirings and made a huge mess when trying to display the final product. It would also made the usage of shared power and ground more viable instead of using individual power.

Another improvement that could be made is in the team wiring and overall physical connections. Although ribbon cables were used, the wiring layout became messy and difficult to follow, which 
reduced the overall organization and visual clarity of the system. In addition, the PCB designs were not effiecently laid out, leading to reduced readability and less efficient connections. 
Significant improvements could be made in PCB component placement to improve board organization, reduce wiring complexity, and minimize potential electrical noise.

Another area for improvement was project time management. As a team, we lost track of time during development, which negatively affected overall project integrity and resulted in rushed or incomplete sections of the system. This can be improved through team communication and planning.
