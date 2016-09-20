## 2. Analysis of Strength of Biometric Authentication
During authentication, a typical biometric system follows a flow whereby:

1.	A biometric pattern is presented.
1.	That data is captured via a sensor.
1.	Signal processing of captured data typically takes place.
1.	A comparison of the captured data occurs, against reference data retrieved from storage.
1.	An authentication decision is made.

The diagram below depicts 11 points in a system where an attacker could potentially interject into the flow to interfere with the decision.<sup>2</sup> These 11 elements may all be self-contained within a single device (such as a mobile device) or distributed across multiple physical systems.

![](media/attackdiagram.png)
*Figure 1 – Biometric system attack diagram*

Many of these vulnerabilities fall into familiar categories that are found in other authentication systems, such as protecting data in transit or at rest, and cyber security controls should be used to mitigate such risks for biometric systems in the same way as other information systems. There are two notable vulnerabilities that fall outside the protection that can be provided by core cyber security controls:

- **Presentation Attack (1)** – This marks the point at which an attacker may present a fake biometric to a sensor. The failure rate of the system to detect an imposter making a presentation attack may generally be referred to as the **PADER**.
- **Override Comparator (6)** – This point of vulnerability relates to the sub-process of the comparator, which is the algorithm that compares an input from the sensor to a stored biometric sample for a user. The performance of the comparator depends on two major factors: how distinctive the biometric pattern is (i.e., the modality's innate features and how many distinct individual patterns may exist) as well as the approach of a vendor's algorithm to analyze the modality.

The focus on these two specific aspects of biometric systems is based on their unique characteristics relating to capturing, processing, and matching data during biometric authentication. We assume that the biometric system incorporates adequate baseline security (i.e., core security controls are in place). Failure to maintain proper baseline security will result in a system that can be attacked by non-biometric-specific means and renders any inherent strength of function score invalid. 

With these factors taken into consideration, the proposed strength equation is based on isolating the quantifiable aspects of these biometric technologies for a measure of inherent strength. The variables for the strength equation are covered in this document and include:

- **FMR and FNMR** - FMR is the probability of a false match occurring during the comparison phase, and likewise, FNMR is the probability of false non-match occurring during the comparison phase. The relevant error rate depends upon the attack scenario, as will be discussed below (the relationship between these errors will be described in the following section).
- **PADER** - The probability of a successful presentation attack during presentation of the biometric sample.
- **Effort** - In addition to FMR and PADER, the strength equation includes Effort to account for the combination of time, knowledge, resources, and potential consequences tied to conducting an attack.

We posit that FMR and PADER can be combined to produce a measure of strength that could be related to concepts such as password entropy. As such, FMR and PADER are the two key components of inherent biometric system strength, but the level of Effort required to attack an authentication system should also be considered, as an attack that requires a level of Effort that is disproportionate to the reward may deter attackers.

With FMR, PADER, and Effort serving as the major inputs, we state that SOFA is proportional to:

![](media/zeroinfosofa.png)

This equation represents a “zero-information” or *“a priori”* attack scenario where the attacker is not aiming to masquerade as a specific individual but is attempting to gain access by chance. In this case, a successful attack requires defeating the presentation attack detection (PAD) and having a successful match with the template in the system. This is analogous to a "brute force" attack on passwords. 

The equation for a “targeted” attack scenario is modified to reflect that, in this scenario, the attacker would create a sample that closely resembles an approved individual’s biometric characteristics. An attack in this scenario only needs to defeat the PAD. In other words, a targeted attacker would present biometric characteristics to a sensor that match a legitimate user. Therefore, the FNMR accounts for the potential for error of the matching algorithm. In this case, we state that SOFA is proportional to:

![](media/targetedsofa.png)

