# Work Log 2026

## 05/01/2026

### App development
*Tags: #Maintenance #App*

*   Created an online maintenance app to follow up on Cloos maintenance more thoroughly.

### Cloos
**Project:** 25380 (hkw7 Oranjewind) | **Part:** 340101 (Tubular)
*Tags: #Programming #Setup*

*   Root settings
*   Root gap opening will be set to 3 mm
*   Drawing altered without informing us, the offline robot program needs checking
*   Parts are not equally cut, which makes programming take longer, as we need to figure out the discrepancy for different weld volumes

### Yaskawa
*Tags: #Quality #Transport*

*   UT on the last piece was Ok, so the adaptation on the root welding with one extra pass was sufficient to avoid any porosity or lack of fusion.
*   Now need to make it ready for transport

## 06/01/2026

### Cloos
**Project:** 25380 (hkw7 Oranjewind) | **Part:** 340101 (Tubular)
*Tags: #WeldVolume #DevOPM*

*   Continuation of filling
*   Weldvolume is not really set up good, still figuring out the average weldvolume to best fill the parts.
*   DevOPM should be set up and tested, need to create extra points to set this up.
    *   Filling can be done with sspd (20,20)
    *   Probably only caplayer needs to have devopm implemented
        *   Caplayer change from 3 beads to 4 beads

## 07/01/2026

### Cloos
**Project:** 25380 (hkw7 Oranjewind) | **Part:** 340101 (Tubular)
*Tags: #Filling #Quality*

*   Continuation of filling
*   Filling is done, weldvolume still needs to be set up better to have an equal distribution for the different cuts
*   UT needs to be checked on first pieces

### Yaskawa
*Tags: #Transport #Logistics*

*   Prepare for transport
    *   Controller, powersource and welding cell base will be transported to SPB site tav Dirk T'jampens
    *   Cobot itself will be taken along with Arne Reabel to SPB to avoid any damage
    *   Plan is to go Monday 12/01/2026 05h00

## 08/01/2026

### Cloos
**Project:** 25380 (hkw7 Oranjewind) | **Part:** 340101 (Tubular)
*Tags: #RootWelding #Testing*

*   Continuation of filling
*   Root gap opening is 2mm on the 2nd piece,
    *   This setup is a test for the robot to do the root welding with this variation
*   The gasflow is reduced to 15 l/min,
    *   Checking the problem, Pedro cannot weld like this as pores are forming

### Teqram
*Tags: #Issue #Robot #Blasting*

*   Some problems with attachment of the tools to the robot
*   Seems like the steel blasting iron pellets are jumping out of the machine to the robot.
    *   This is a problem with the machine as then the robot cannot attach the tool to the robot
        *   The small pellet is enough to trigger the robot alarm

## 09/01/2026

### Cloos
**Project:** 25380 (hkw7 Oranjewind) | **Part:** 340101 (Tubular)
*Tags: #Gasflow #Troubleshooting #Maintenance*

*   Continuation of filling
*   Gasflow problem is not fixed, examining
    *   Checked nipple of gashose, checked manometer, changed hosepacket, duodrive torch, gashose to the wirefeeder, automatic valve for the gasflow in the wirefeeder, checked everything for leakage.
        *   The valve in the wirefeeder is not opening completely, taken the old valve from the old wirefeeder to check.
    *   Problem is fixed the valve was the problem, Geert from maintenance replaced the valve from the new feeder with old one.
        *   Probably the working on the line had contaminated the valve,
        *   Also being at the end of the line is not really helping.
*   Gasflow is now 20 l/min,
    *   Pedro welded like this but more pores are forming
        *   Pores are forming specifically against the attached plate, not against the Tube itself which is clear of pores
            - <a href="images/25380_340101_pores_1.jpg"><img src="images/25380_340101_pores_1.jpg" width="150" title="Click to enlarge" /></a>
            *   Closer inspection reveals that the weld itself is good as we grinded parts away to check
                *   The problem is the attached plate as the pores are forming there
                    *   Increasing the gasflow did not help as we thought that was the problem

### Teqram
*Tags: #Issue #Collision #Procedure*

*   Some problems with attachment of the tools to the robot
    *   Frank posted the same problem in the whatsapp groupchat.
        *   Cover plate needs to be reattached to the toolstation.
*   Adjusted the lin_30_rounded procedure as it was colliding with flipper effectors in the software due to improper placement of the part on the effector triggers the software to have a collision immenent and stops the robot
    *   Adjusted the last step of the procedure to have it vertically move up by -3mm from 19 to 16
    *   Problem is fixed and is still grinding the parts properly, hardness is ok and coverage is good throughout the parts.
        *   Probably this fix is also needed for other procedures that have thickness less than 30mm
        *   Above 30 mm the robot is not colliding with the flipper effectors
            *   The part thickness is sufficient to have the overlap reasonably large without triggering warnings
