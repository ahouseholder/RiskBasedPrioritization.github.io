# Introduction

!!! abstract "About this Guide"

    This Risk Based Prioritization Guide is a pragmatic user-centric view of risk, the related standards and data sources, and how you can apply them for an effective Risk Based Prioritization for your organization.

    It is written by, or contributed to, some of the thought leaders in this space **for YOU.**

    [CISA](https://www.cisa.gov/news-events/directives/bod-22-01-reducing-significant-risk-known-exploited-vulnerabilities), [Gartner](https://www.gartner.com/smarterwithgartner/focus-on-the-biggest-security-threats-not-the-most-publicized) and others, recommend focusing on vulnerabilities that are known-exploited as an effective approach to risk mitigation and prevention, yet very few organizations do this. Maybe because they don't know they should, why they should, or how they should? This guide will cover all these points.


!!! success "After reading this guide you should be able to"
    1. Understand Risk 
          1. the main standards and how they fit together
          2. the key risk factors, especially known exploitation or likelihood of exploitation
    1. Prioritize CVEs by Risk
          1. apply this understanding to Prioritize CVEs by Risk for your organization resulting in
             1. a significant reduction in your security effort
             2. a significant improvement in your security posture by remediating the higher risk vulnerabilities first
    2. Apply the provided guidance to your environment
          1. the source code used to do much of the analysis in this guide is provided - so you can apply it to your internal data
          2. compare what other users, and tool vendors, are doing for Risk Based Prioritization so you can compare it to what you're doing
          3. ask more informed questions of your tool/solution provider

## Overview

The guide covers:

1.  Risk
    1.  The Vulnerability Landscape covering the main standards and how they fit together
    2.  What these standards and risk factors look like for different populations of CVEs
    3.  How to use the standards and data sources in your environment
2.  How the standards and data sources are being used using real examples
    1.  How some vendors are using them in their tools
    2.  How some users are using them in their environments
3.  Applying all this for Risk Based Prioritization 

!!! tip
    :material-play-box-edit-outline: on a menu item indicates the content is more hands on - applying the content from the guide.

    "🧑‍💻 Source Code" on a page is a link to the source code used to generate any plots or analysis on public data.

## Intended Audience

The intended audience is people in these roles:

- Product Engineer: the technical roles: Developer, Product Security, DevSecOps
- Security Manager: the non-technical business roles: includes CISO
- Cyber Defender: network defenders,  IT/infosec
- Tool Provider: Tool providers: Tool Vendors, open source tools,...

This is a subset of the Personas/Roles defined in the Requirements chapter.

No prior knowledge is assumed to read the guide - it provides just enough information to understand the advanced topics covered.

A basic knowledge of Jupyter Python is required to run the code (with the data provided or on your data).


## How to Use This Guide

1. For the short version, read these sections and understand the Risk Based Prioritization Models:
      1. Risk (back of the napkin model)
      2. Vendors - Qualys (Qualys scoring applied with EPSS)
      3. Organizations - Yahoo (Decision Trees)
2. For a deeper understanding read the full guide.
3. To get the most out of this guide, also play with the code - and analyze your data.


Each of the Risk Based Prioritization Models above use similar risk factors (known exploitation and likelihood of exploitation, with variants of CVSS base metrics parameters or scores) but in very different ways to rank/score the risk/priority. The outcome is the same - a much more granular prioritization at the high end of risk than offered by CVSS.

If you're looking for the "easy button", or the one scheme to rule them all for Risk Based Prioritization, you won't find it (here or anywhere else).

## How to Contribute to This Guide

You can contribute content or suggest changes via a Github PR or comment TODO insert link.

Multiple independent data and reference inputs would really help:

- If you're a tool/solution vendor, and would like to provide anonymized, sanitized data - or what scoring system you use and why
- If you'd like to share what your organization is doing (anonymized, sanitized as required) as a good reference example

## Foreword by Chris Madden
I embarked on this Risk Based Prioritization journey because, as a Product Security engineer, my role is to enable the flow of software/value to our customers by helping deliver high quality software efficiently and securely.

A large part of that was to be able to prioritize vulnerabilities by Real Risk. Lots of dumb questions and data analysis later, this guide represents the distillation of that knowledge into a user-centric system view - what I wish I knew before I started - and learnt by interacting with other users, standards groups, and tool vendors. There's a friendly vibrant community in this space.


## Source Code
1.  See https://github.com/epss-sig/epss-interoperability TODO
    for the code
    1.  This includes the data used in the analysis (downloaded
        Jan 13) and how to download it
2.  This code is licensed under the Apache 2 Open Source License.
## Notes

1. This guide is not affiliated with any Tool/Company/Vendor/Standard/Forum/Data source. 
    1. Mention of a vendor in this guide is not a recommendation or endorsement of that vendor. 
          1. The choice of vendors was determined by different contributors who had an interest in that vendor.

2.  This guide is a living document i.e. it will change and grow over time - with your input.

## Alternative or Additional Guidance

The "writing style" in this guide is "succinct and opinionated" i.e. data analysis plots (with source code where possible) and observations and takeaways that you can assess against your data and environment.

It is not a verbose treatment of topics with broader or background context. For that, consider the following (no affiliation to the author): 

-  [Effective Vulnerability Management: Managing Risk in the Vulnerable Digital Ecosystem](https://www.amazon.com/Effective-Vulnerability-Management-Vulnerable-Ecosystem/dp/1394221207) 
  
