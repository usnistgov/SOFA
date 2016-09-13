## 3. FMR and PADER Testing
### 3.1. Matching Error Rates


### 3.2. Determining FMR and FNMR

#### 3.2.1. False Match Rate

#### 3.2.2. False Non-Match Rate

#### 3.2.3. Match Rate Interdependence

#### 3.2.4 Testing Requirements

#### 3.2.4.1 *Testing Best Practices*


### 3.3. Presentation Attack Detection (PAD)

#### 3.3.1. Measuring and Characterizing the Performance of PAD

#### 3.3.2. Reporting, Considerations, and Principles for PAD testing

#### 3.3.3. Limiting the number of unsuccessful attempts
There are limits to what can be learned from testing PAD subsystems due to both the paucity of knowledge regarding how best to conduct testing (e.g. number of subjects versus number of samples) and the inherent uncertainty in this space due to the infinite PAIs that could be used to attack a biometric system and evolving threats over time.  Therefore, a biometric sensor must have a maximum number of unsuccessful attempts, after which the biometric sensor will no longer be available for authentication. That number can be set sufficiently low, such as ten attempts, or it could be related to the testing results and the max IAPMR, so that the limit is equal to or less than half of the number of thwarted attacks observed in testing for the most successful attack type.

## 4. Cyber Hygiene
Many of the vulnerabilities present within a biometric system, as illustrated in the attack diagram in *2. Analysis of Strength of Biometric Authentication*, are mitigated in the same way as vulnerabilities for other form factors.  The two broad categories of these vulnerabilities are protecting data in transit (between sub-processes) and data at rest (within a sub-process).

### 4.1. 800-63-3
Content to be developed using information cited for NIST SP 800-63-3.
