---
layout: post
title: Secure Software Architecture
---
The purpose of this document is to help software engineering organizations implement secure architectures during the development of Android applications. Adding security to a software architecture is not always easy and can be time consuming so this document is aimed to act as a guide to help in the design and development process. Mobile applications can help boost an organizations performance significantly, however they can have costly security flaws for the company. To help mitigate the risks that can occur in a mobile or more specifically android application an organization should develop security requirements and evaluation process to ensure the application is as securely designed as possible. This documents will help guide the software engineering companies in finding out the process that works for them to increase confidence in their systems.

***Introduction***

Within a system there are three types of vulnerabilities known vulnerabilities, unknown vulnerabilities and adversary-created vulnerabilities (Ross, R., McEvilley, M., & Oren, J., 2016). The second two vulnerabilities can be hard for an organization to know without an outside perspective, therefore those become the most dangerous for an organization to protect their system from. No matter how hard a company tries they will never fully be protected from vulnerabilities so their job is to mitigate the risk as much as possible to ensure confidence in their systems. A few ways to address said vulnerabilities would be secure systems architecture techniques/requirements, processes and practices.

***Techniques***

Trustworthy systems can mean many different things for example, free from error, well protected against threats and vulnerabilities and more. From a security perspective, a trustworthy system is a system that meets specific security requirements in addition to meeting other critical requirements (Ross, R., McEvilley, M., & Oren, J., 2016). A way to ensure a trustworthy system is to implement secure architectures during the development phase of applications so you are not playing catch up when vulnerabilities are found later. For the purpose of this proposed process the Microsoft Security Development lifecycle will be taken and applied to Android application development.

{:.center}
![]({{ site.baseurl }}/img/securesoftware.png)

Figure 1.1 Microsoft Security Development Lifecycle (Microsoft, 2017).

***Training***

The first SDL phase is training (Microsoft, 2017). This is a huge part if the process because the software engineering team needs to stay up to date and knowledgeable as new threats and vulnerabilities are discovered and mitigated. It will not do an organization any good if they have a secure architecture set up but are not able to maintain its security. A recommendation would be to make software engineers and others who assist in the software development attend a yearly security training online or in person to ensure they are staying up to date.

***Requirements & Design***

The requirements section lists three practices: establish security and privacy requirements, create quality gates and bug bars, and perform security and privacy risk assessments (Microsoft, 2017).
It is extremely important for an organization to outline their security requirements to ensure everybody is on the same page during the development and implementation of software. This is also the time where a security and privacy analysis should be run. The goal of this practice is to ensure that a minimum security criteria is set and there is a tracking system setup to ensure that the architecture is not only built secure but maintained and monitored. Creating quality gates/bug bars would be equal to defining what the acceptable risk the organization is willing to accept for the software. This is huge as well to make sure organizations are maintaining the same quality on all their android applications.

During the design phase it is important to set a schedule and budget. The organization should develop a plan or threat model for how they are going to address security concerns so they can remain on schedule and not go over budget. During this time it would be recommended to apply the principle of least privilege to help reduce the risk greatly of security issues occurring. If an organization can avoid any security hiccups during this phase it would be idea to stay on budget and schedule. This can be the most time consuming process of the SDL.

***Implementation***

After the design process is finished then comes the implementation phase where the design is put to the test. During this phase it is important to maintain standards with the appropriate tools that software engineers can use on the software. Utilizing current and consistent tools when implementing the software can reduce the risk of a security vulnerability greatly. Code scanning can be done so bugs can be spotted and corrected to help mitigate future risks. There are several great code scanning tools and many coding compilers have these functions built in when executing the code. These can be your best friends when building software and can reduce time and money spent.

***Verification***

In the verification phase Microsoft outlines performing dynamic analysis, fuzz testing and attack surface review (Microsoft, 2017). These are tools that can be used when testing the software for vulnerabilities and serious security flaws. This part of the SDL can be the most time consuming but it also can be the most rewarding and exciting. Kali Linux has software penetration tools as well as many other suppliers. During this phase it is extremely important that you are running and testing your software in real time with end users as well penetration testing, conducting mock attacks and throwing bogus data at the software to check for missed vulnerabilities in the software design or code. Threat models that were created in the previous phases can be utilized as a reference when running these exercises.  The more testing that is done within reason the more the software can be ensured to have a secure architecture and be a trustworthy system.

***Release & Response***

It is important to develop a plan for how the organization will receive feedback on the newly released software. Feedback is crucial to the software success as well helping patch any security holes in the architecture. Before the release of the product an organization wants to do one last security sweep and see if they missed any vulnerabilities that need to be addressed before release. Once all the last checks are done the organization is ready for the release. After the release it is the organization’s duty to stay on top of any security vulnerabilities that are discovered by end users and address them in a timely consistent manner. Just because the software has been designed, developed and released doesn’t mean it will not require maintenance. Staying up on the software security maintenance will continue to mitigate risk and ensure a trustworthy system.

***References***

Quirolgico, S., Voas, J., Karygiannis, T., Michael, C., & Scarfone, K. (2015). Vetting the Security of Mobile Applications. doi:10.6028/nist.sp.800-163

Ross, R., McEvilley, M., & Oren, J. (2016). Systems Security Engineering, Considerations for a Multidisciplinary Approach in the Engineering of Trustworthy Secure Systems. doi:10.6028/nist.sp.800-160

Microsoft Security Development Lifecycle. (n.d.). Retrieved March 27, 2017, from https://www.microsoft.com/en-us/sdl/
