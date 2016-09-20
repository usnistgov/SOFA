## 1. Intro

There are many different methods for authenticating users to applications, devices, and services, from “traditional” user names and passwords, to software one-time passwords, to multiple modalities of biometric systems. Each authentication factor brings a unique set of security and user experience characteristics as well as potential vulnerabilities. With all these options, and the persistent drive towards stronger authentication, the emerging question is: “which technology fits my risk environment?” 

There is no established standardized method for comparing and combining authentication mechanisms, in part due to the wide array of available technologies. The establishment of a common framework for measuring, comparing, and combining (such as in multi-factor implementations) authenticator strength could enable greater alignment of identity practices with organizational risk and promote greater federation and interoperability across sectors, markets, and enterprises. At a workshop on January 12 and 13, 2016, NIST presented a proposed starting point for this framework with a focus on biometric technologies.<sup>1</sup> This paper represents a further refinement of this work and outlines a process intended to support the evaluation of biometric authenticators and—ultimately—multiple authentication mechanisms. 

Why choose biometrics as a starting point? As an ever-expanding number of transactions are being invoked within mobile applications, biometric mechanisms built into smartphones and connected devices increasingly address user authentication. The result is a diverse and flourishing ecosystem, but one that generally lacks standards and guidance, that allow organizations to better understand the answers to questions such as: How well do the biometric systems work? How does their configuration impact the strength of the authentication event? How well do they protect against spoofing attacks? How does their performance impact security? How can they be effectively combined with other factors and what is the resulting strength of authentication? These are the very questions that the Strength of Function for Authenticators—or SOFA—framework is intended to address. 
 


### 1.1.	Purpose
This document proposes a framework for the measurement of biometric system strength and begins to consider its placement within a broader framework for strength of authentication. The framework is focused on positive authentication and one-to-one comparisons (i.e., not identification applications such as watch-list activities).

By advancing the ability to measure the strength of authentication for biometrics within an evaluation framework, this document seeks to:

-	Develop a greater understanding of the strength of biometric solutions.
-	Improve the alignment of their use with organizational risk-based decisions.
-	Enhance the ability of organizations to compare and combine different biometric and other authentication systems.
-	Provide guidance relating to biometric authentication system security and the protection of personal data.

Given organizations’ shift toward developing and implementing biometric solutions across a broad range of applications and channels, this framework is designed to provide a level of quantitative assurance to organizations that are seeking to use biometric technology to mitigate risk.

This paper will:

-	Present a **strength equation** to represent the **Strength of Function for Authenticators (SOFA)** with a focus on **SOFA-Biometrics (SOFA-B)**. SOFA-B includes variables for **False Match Rate (FMR)** and **False Non-Match Rate (FNMR)**, **Presentation Attack Detection Error Rate (PADER)**, and **Effort** required to perform the attack.
-	Provide guidance for the **baseline security** required for authentication systems, so that areas not specific to biometric technologies are covered by core security controls **(good baseline security)**.

The framework considers two attack perspectives—“zero-information” and “targeted” attacks. It is modality agnostic, and is intended to be flexible to suit an organization’s own unique environment and needs. 
