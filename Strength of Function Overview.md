## 2. Analysis of Strength of Biometric Authentication
During authentication, a typical biometric system follows a flow whereby:

1.	A biometric pattern is presented.
1.	That data is captured via a sensor.
1.	Signal processing typically takes place.
1.	A comparison of the captured data occurs, against reference data retrieved from storage.
1.	An authentication decision is made.

The diagram below depicts 11 points in a system where an attacker could potentially interject into the flow to interfere with the decision<sup>2</sup>. These 11 elements may all be self-contained within a single device (such as a mobile device) or distributed across multiple physical systems.

![](media/attackdiagram.png)

Many of these vulnerabilities fall into familiar categories that are found in other authentication systems, such as protecting data in transit or at rest, and cyber security controls should be used to mitigate such risks for biometric systems in the same way as other information systems. There are two notable vulnerabilities that fall outside the protection that can be provided by core cyber security controls:

- **Presentation Attack (1)** – This marks the point at which an attacker may present a fake biometric to a sensor. The failure rate of the system to detect an imposter making a presentation attack may generally be referred to as the **PADER**.
- **Override Comparator (6)** – This point of vulnerability relates to the sub-process of the comparator, which is the algorithm that compares an input from the sensor to a stored biometric sample for a user. The performance of the comparator depends on two major factors: how distinctive the biometric pattern is (i.e., the modality's innate features and how many distinct individual patterns may exist) as well as the approach of a vendor's algorithm to analyze the modality.

The focus on these two specific aspects of biometric systems is based on their unique characteristics relating to capturing, processing, and matching data during biometric authentication. We assume that the biometric system incorporates an adequate level of “cyber hygiene” (i.e. core security controls are in place). Failure to maintain proper cyber hygiene will result in a system that can be attacked by non-biometric-specific means and renders any inherent strength of function score invalid. 

With these factors taken into consideration, the proposed strength equation is based on isolating the quantifiable aspects of these biometric technologies for a measure of inherent strength. The variables for the strength equation are covered in this document and include:

- **FMR** - The probability of a false match occurring during the comparison phase.
- **PADER** - The probability of a successful presentation attack during presentation of the biometric sample.
- **Effort** - In addition to FMR and PADER, the strength equation includes Effort to account for the combination of time, knowledge, resources, and potential consequences tied to conducting an attack.

We posit that FMR and PADER can be combined to produce a measure of strength that could be related to concepts such as password entropy. As such, FMR and PADER are the two key components of inherent biometric system strength, but the level of Effort required to attack an authentication system should also be considered, as an attack that requires a level of Effort that is disproportionate to the reward may deter attackers.

With FMR, PAD, and Effort serving as the major inputs, we state that SOFA is proportional to:

![](media/zeroinfosofa.png)

This equation considers a “zero-information” or *“a priori”* attack scenario where the attacker is not aiming to pose as a specific individual but is attempting to gain access by chance.  This is analogous to a "brute force" attack on passwords. The equation for a “targeted” attack scenario is changed to reflect that the attacker would likely create a sample that closely resembles an approved individual’s biometric characteristics and therefore the True Match Rate, or one less the False Non-Match Rate (FNMR), is a better approximation (than the FMR) for the probability of a successful attack.

![](media/targetedsofa.png)

### 2.1. Effort
[This section is a place holder. Contributions are welcome. And more will more developments will be inserted here following the GIS workshop on September 20, 2016.]

The level of effort required to attack a biometric authentication system varies across the two scenarios under consideration:  “zero-information” and “targeted” attacks. The following table lists some of the potential factors and techniques that could affect the level of effort required for attacks on password/PIN-based systems and biometric-based systems. 

| Password/PIN         | Biometrics     |
| -------------------  |----------------|
| Zero-information: <br> -Length and complexity | Zero-information: <br> -Sample size and complexity <br> -Access to sensor/device <br> -Computational complexity of matching         |  
| Targeted: <br> -Shoulder surfing <br> -Checking notepads | Targeted: <br> -Retrieving the biometric sample <br> -Creating an artefact |

Biometric attacks generally require more effort than attacks on PINs and passwords. Whereas the complexity of attacking a password with no prior information is based solely on the entropy of that password, “zero-information” biometric attacks may require determining the scope of the biometric sample based on factors such as:  creation of the sample and computational complexity. 

We presume that “targeted” biometric attacks require obtaining a valid sample and recreating it for use during presentation, and this may also require substantial time, knowledge, and resources.

How effort is determined is not yet established, though time, knowledge, and resources required for an attack may contribute to this measure. The potential consequences for an attacker being caught against the value gained from a successful attack may also be considered. However, any number of factors could be incorporated may vary across modalities. Future efforts may benefit from a normalized scale that spans across authenticator types for the purpose of comparison. 



<sup>2</sup>Inspired by vulnerability diagram in ISO/IEC 30107-1: 2016 and N.K. Ratha, J.H. Connell, R.M. Bolle, “Enhancing security and privacy in biometrics-based authentication systems,” IBM Systems Journal, Vol 40. NO 3, 2001.
