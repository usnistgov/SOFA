## 1. Intro

Today there is a plethora of different methods for authenticating users to applications, devices, and services, 
from “traditional” user names and passwords, to out-of-band SMS messages, to multiple modalities of 
biometric systems. Each authentication factor brings to the table a unique set of security and user experience characteristics 
as well as potential vulnerabilities. With all these options, and the persistent drive towards stronger authentication, 
the emerging question is “which technology fits my risk environment, today?” Currently, there is no established standardized 
method for comparing and combining authentication mechanisms, in part due to this wide array of technologies that are available. 
However, the establishment of a common framework for measuring, comparing, and combining (such as in multi-factor implementations) 
authenticator strength could enable greater alignment of identity practices with organizational risk andpromote greater federation 
and interoperability across sectors, markets, and enterprises.  At a workshop event<sup>1</sup>  on January 12 and 13, 2016, NIST 
presented a proposed starting point for this framework with a focus on biometric technologies. This paper represents a further 
refinement of this work and outlines a process intended to support the evaluation of biometric authenticators 
and—ultimately—multiple different authentication mechanisms. 

Why choose biometrics as a starting point? As an ever-expanding number of transactions are being invoked in mobile 
applications, the question of effectively authenticating users is increasingly being addressed by biometric mechanisms 
built into smart phones and connected devices. The result is a diverse and flourishing ecosystem, but one that currently 
lacks generalized standards and guidance, so that organizations can better understand the answers to questions such as: 
How well do the biometric systems work? How does their configuration impact the strength of the authentication event? 
How well do they protect against spoofing attacks? How does their performance impact security? How can they be effectively 
combined with other factors and what is the resulting strength? These are the very questions that the 
Strength of Function for Authenticators—or SOFA—framework is intended to address and as a result represents the ideal 
starting place for the effort. 


### 1.2.	Purpose
This document proposes a framework for the measurement of biometric system strength and begins to consider its placement
within a broader framework for strength of authentication. The framework is focused on positive authentication and one-to-one 
comparisons (i.e., not identification applications such as watchlisting).

By advancing the ability to measure the strength of authentication for biometrics within an evaluation framework, 
this document seeks to:
- Develop a greater understanding of the strength of biometric solutions.
- Improve the alignment of their use with organizational risk-based decisions.
- Enhance the ability of organizations to compare and combine different biometric and other authentication systems.
- Provide guidance relating to biometric authentication system security and the protection of personal data.

Given the shift in organizations towards developing and implementing biometric solutions across a broad range of 
applications, this framework is designed to provide a level of quantitative assurance to organizations that are 
seeking to use biometric technology to mitigate risk.

This paper will:
- Present a strength equation or ratio to measure the Strength of Function for Authenticators (SOFA), which includes 
variables for False Match Rate (FMR), Presentation Attack Detection Error Rate (PADER), and Effort required to perform 
the attack.
- Provide guidance for the baseline security required for authentication systems, so that areas not specific to 
biometric technologies are covered by core security controls (good cyber hygiene).

The framework considers two attack perspectives (“zero-information” and “targeted” attacks). Additionally, 
the approach to this framework is modality agnostic and intended to be flexible to suit an organization’s own 
unique environment and needs. 



<sup>1</sup>“Advanced Identity Workshop: Applying Measurement Science in the Identity Ecosystem” at NIST’s Gaithersburg, MD campus.
