## 3. FMR and PADER Testing
### 3.1. Matching Error Rates
Statistical analysis is essential when evaluating the performance and accuracy of matching algorithms and systems. Two characteristics of this analysis are of particular importance: Type 1 and Type 2 errors, or False Match Rate (FMR) and False Non-Match Rate (FNMR), respectively. 
This document focuses on FMR, rather than FNMR, and how it affects the measurement of strength of an authentication system. According to [MINEX04], FNMR is best described as a measure of user inconvenience, while FMR is highly regarded as a “measure of security.” These different measurements indicate how similar one sample is to another through pattern matching and recognition algorithms. 
A suitable biometric modality (e.g., fingerprint, face, iris, etc.) should be able to consistently distinguish a biometric pattern as uniquely belonging to an individual – and not to others who may attempt to access the individual’s account.  Said another way, intra-class variability needs to be sufficiently small, and the inter-class variability needs to be sufficiently large. Intra-class variability refers to the variations of a biometric pattern of the same modality from the same user while inter-class variability refers to the similarity of a biometric pattern between different individuals.

### 3.2. Determining FMR and FNMR
#### 3.2.1. False Match Rate
A zero-effort imposter attempt occurs when “an individual submits his/her own biometric characteristics as if he/she were attempting successful verification against his/her own template, but the comparison is made against the template of another user.” [From ISO/IEC 19795-1:2006]  When this results in a match, it is called a false match.  False Match Rate is defined<sup>3</sup> as the “proportion of zero-effort imposter attempt samples falsely declared to match the compared non-self template.” In other words, out of a total number of imposter attempts, false match rate is the percentage of those attempts that improperly result in a match, based on a set threshold.

#### 3.2.2. False Non-Match Rate
A genuine transaction signifies that the probe and gallery samples are from the same individual and should result in a match. False Non-Match Rate is defined<sup>4</sup> as the “proportion of genuine attempt samples falsely declared to not match the template of the same characteristic from the same user supplying the sample. In other words, out of a total number of legitimate attempts, false non-match rate is the percentage of those attempts that improperly results in a non-match, based on a set threshold.

#### 3.2.3. Match Rate Interdependence
When comparing two biometric samples, the similarity scores of the imposter distribution will generally be lower than the scores of the genuine distribution.  However, there is overlap.  In other words, there is not a value that will clearly demarcate matches and non-matches.  So a score must be selected as a decision threshold in order to balance the security and convenience required of an application.  The decision threshold (or operating point) signifies the minimum similarity score that an algorithm needs to return when comparing two samples to yield a positive match decision.  If the threshold is varied, it changes both the FMR and FNMR:  an increase in the decision threshold would decrease the FMR but increase the FNMR, and a decrease of the threshold would increase the FMR but decrease the FNMR.

#### 3.2.4 Testing Requirements
Empirical testing is required to determine the FMR of a biometric system, which is a test of the distinctiveness of the modality as well as the ability of the algorithm to discriminate between patterns.  Testing requirements for biometrics are covered in ISO/IEC 19795-1 (and other parts of ISO/IEC 19795 depending on testing needs.)  ISO/IEC 19795-1 provides formulae for the number of subjects that need to be tested for statistically significant results.

#### 3.2.4.1 *Testing Best Practices*
The distribution of sample data is critical to measuring performance characteristics when testing algorithms. To obtain the most accurate results, the sample data should be distributed in a way that best reflects samples that will be collected while in operation. One way to verify performance measures is to run internal testing on in-house data. While this is good for initial testing and validation, third-party testing should be done to produce unbiased and independent results.<sup>5</sup>

### 3.3. Presentation Attack Detection (PAD)
One of the challenges for implementing biometric authentication is deploying safeguards to avoid presentation attacks, commonly known as biometric spoofing. This is especially true in uncontrolled environments where there is not an operator monitoring the placement or capture of a biometric.  There are multiple ways to mitigate the risk of a successful presentation attack. The class of methods created to directly counter these attempts at the biometric sensor is known as Presentation Attack Detection (PAD). Examples of PAD include Artefact Detection (AD) and Liveness Detection (LD).

Presentation Attack Detection (PAD) is defined by ISO/IEC 30107-1:2016 as “automated determination of a presentation attack,” which is a “presentation to the biometric data capture subsystem with the goal of interfering with the operation of the biometric system.”

Error rates for PAD are expressed as classification errors.  A PAD subsystem may incorrectly classify a bona fide presentation as an attack presentation or vice versa.  To measure the strength of function for biometric authentication, the error of interest occurs when a PAD subsystem fails to detect an attack presentation, allowing an attacker positive access to an authorized user’s account.<sup>6</sup>

At the PAD subsystem level, this error rate is known as the Attack Presentation Classification Error Rate (APCER) and is defined as the “proportion of attack presentations using the same PAI species incorrectly classified as bona fide presentations at the PAD subsystem in a specific scenario.”<sup>7</sup>  At the biometric system level, this error rate is called the Imposter Attack Presentation Match Rate (IAPMR), which expresses the ratio of imposter attack presentations, all made with the same material, that are successfully matched to the targeted user (at a fixed operating threshold for the matching algorithm). In other words, IAPMR is the measure of the ability of a spoofed biometric to not only bypass the PAD subsystem but to be authenticated as a bona fide user.

#### 3.3.1. Measuring and Characterizing the Performance of PAD
PAD error rates, such as IAPMR, must be determined through empirical testing.  The goal for PAD testing is to test a set of materials (Presentation Attack Instrument [PAI] species) that represent an attack potential level and determine the max error rate found among those materials.  

Prior to testing, the initial step must be taken to identify the use case for the biometric product. The specific application will have an expected level of risk or attack potential<sup>8</sup>, for which a set of PAI species should be evaluated to determine if the biometric system rejects all of the PAI species at or below a maximum threshold for IAPMR.  The max IAPMR across all tested PAI Species (PAIS) is the value to be used in the SOFA-B proportion for IAPMR.  In other words, the IAPMR that is used to characterize the expected PAD error at a given attack potential is the IAPMR of the most successful attack. 

Attack potential levels may be associated with PAI Species that represent increasing levels of effort to mount an attack and/or a criteria for the following characteristics, to more broadly describe level of effort needed to mount an attack:  time; expertise; equipment; and source of the biometric characteristic.  Table 1 shows examples of both approaches.

![](media/attackpotential.png)

#### 3.3.2. Reporting, Considerations, and Principles for PAD testing
Testing and reporting requirements are provided in ISO/IEC DIS 30107-3.  There are additional aspects of testing that need to be considered to carry out an evaluation, including:
- How many subjects should be represented in the N samples that are tested? Is it best to have as few as possible, as many as possible, or a diverse set with a small number of replicates per subject?
- What size should N be for statistical significance? What amount of error can be tolerated?

The following represent current best practices and principles for PAD testing.
- Testing by an independent party yields more reliable results for relying parties/consumers.
- Specifics about some PAIS/materials/recipes that will be tested should be kept secret.  The company submitting a product for testing should not know every type of attack that their system will be evaluated against. 
- Certification of PAD performance should have an expiration date and should not be valid for many years.
- Test results are more likely to reflect real word results if the test data is representative of operational data.  

#### 3.3.3. Limiting the number of unsuccessful attempts
There are limits to what can be learned from testing PAD subsystems due to both the paucity of knowledge regarding how best to conduct testing (e.g. number of subjects versus number of samples) and the inherent uncertainty in this space due to the infinite PAIs that could be used to attack a biometric system and evolving threats over time.  Therefore, a biometric sensor must have a maximum number of unsuccessful attempts, after which the biometric sensor will no longer be available for authentication. That number can be set sufficiently low, such as ten attempts, or it could be related to the testing results and the max IAPMR, so that the limit is equal to or less than half of the number of thwarted attacks observed in testing for the most successful attack type.

## 4. Cyber Hygiene
Many of the vulnerabilities present within a biometric system, as illustrated in the attack diagram in *2. Analysis of Strength of Biometric Authentication*, are mitigated in the same way as vulnerabilities for other form factors.  The two broad categories of these vulnerabilities are protecting data in transit (between sub-processes) and data at rest (within a sub-process).

### 4.1. 800-63-3
Content to be developed using information cited for NIST SP 800-63-3.

<sup>3</sup> ISO19795-1

<sup>4</sup> Also pulled from ISO19795-1.

<sup>5</sup> Generalized best practices can be found in ISO19795-1 while guidance on modality-specific testing can be found in ISO19795-3.

<sup>6</sup> Note that SOFA is intended to measure the strength of positive authentication use cases, when both authorized users and attackers want to gain positive logical or physical access. SOFA does not cover negative access, or watchlisting applications, when the attacker is incentivized to not be recognized.

<sup>7</sup> ISO/IEC 30107-1:2016.

<sup>8</sup> Defined as “measure of the effort to be expended in attacking a TOE, expressed in terms of an attacker's expertise, resources and motivation”.
