---
title: "Google Summer of Code 2018 ideas list"
excerpt: "Ideas page for GSoC 2018."
header:
  teaser: /assets/images/logo-gsoc.png
tags:
  - news
author_profile: false
sidebar:
  nav: "news"
last_modified_at: 2018-01-20T12:08:02+02:00
---

This year, GNSS-SDR is applying again to serve as a mentoring organization for [Google Summer of Code](https://summerofcode.withgoogle.com/) (also known as GSoC), a global program that offers students stipends to write code for open source projects. In order to participate in the program, you must be a student. Google defines a student as an individual enrolled in or accepted into an accredited institution including (but not necessarily limited to) colleges, universities, masters programs, PhD programs and undergraduate programs. You should be prepared, upon request, to provide Google with transcripts or other documentation from your accredited institution as proof of enrollment or admission status. Computer Science does not need to be your field of study in order to participate in the program. You may be enrolled as a full-time or part-time student for a time period that includes April 23, 2018, and must be at least 18 years old to be eligible to participate in Google Summer of Code in 2018.

If you are an eligible and interested student, read through the list and note the projects you are interested in. You, as the student programmer, then submit a proposal to Google, using the [GSoC 2018 website](https://summerofcode.withgoogle.com/). If GNSS-SDR is among the accepted mentoring organization, the application form for students will be open from March 12 16:00 UTC until March 27 16:00 UTC. We recommend you to submit your application early. By doing so, it will be given a greater share of attention than is possible for applications submitted at the last minute.

You might submit a proposal following the guidelines below, or you might want to adapt them to your needs. Changes to the proposal could include:

  * You think the project as suggested is too large and you can only feasibly complete part of it; if so, make sure your proposal covers a reasonable subset of the functionality (that is, something which is useful without the rest of the project being implemented).

  * You think the project as suggested is too small; in this case you might want to extend the idea, combine projects, etc.

  * You like the basic idea of the project but it is not such a good fit for the skills that you have; in this case please feel free to suggest an alternative, but try to remember that the idea is for the software to be useful for its existing and potential users.

Your proposal should include the following: your project proposal, why you would like to execute on this particular project, and the reason you are the best individual to do so. Your proposal should also include details of your academic, industry, and/or open source development experience, and other details as you see fit. An explanation of your development methodology and schedule is a good idea, as well. It is always helpful to include your contact information, as it will not be automatically shared with your would-be mentors as part of the proposal process.

Hereafter we list, in no particular order, some proposals for projects to be carried out by the students participating in GSoC 2018. This is by no means a closed list, so the students can feel free to propose alternative activities related to the project.

-------

## Robust Kalman Filter-based Tracking Techniques for Advanced GNSS Receivers

### Description:

Tracking of synchronization parameters (*i.e.*, time-delay and carrier phase) is a key step in the core of any GNSS receiver. The current tracking block implementations, which are fully operational in GNSS-SDR for GPS L1, GPS L2, GPS L5, Galileo E1, Galileo E5a and GLONASS L1 bands, are based on traditional tracking loop architectures (e.g., DLL and PLL). Those techniques are prone to fail in non-nominal propagation conditions such as high-dynamics, shadowing, strong fadings, multipath effects or ionospheric scintillation. It is known that Kalman filter (KF)-based techniques, which are formulated from an optimal filtering standpoint, are more robust to such harsh propagation conditions, thus being the methods of choice in advanced GNSS receivers.

The main goals of this project are: *i*) to develop and integrate into the GNSS-SDR core standard (discriminator-based) KF tracking techniques for both (joint) code and phase tracking; *ii*) extend such standard KFs to adaptive KF tracking, for instance, sequentially adjusting the measurement covariance at the output of the discriminators; *iii*) implement discriminator-free extended KF (EKF) solutions, and *iv*) to test and compare the performance of these techniques with respect to traditional architectures using real signals.

### Skills required:

Good understanding of statistical signal processing and C++ programming (familiarity with the [GNU Radio](http://gnuradio.org) framework and Kalman filtering techniques is a plus).

### Potential mentor(s):

Dr. Jordi Vil&agrave;-Valls, Dr. Pau Closas, Dr. Javier Arribas.

-------


## Robust Cross-ambiguity function for anti-jamming

### Description:

Although strong jamming can overwhelm much weaker GNSS signals, receiver performance can be significantly improved by implementing interference mitigation techniques. Robust statistics was recently explored as a mitigation technique that requires minimal receiver modifications, while providing unprecedented anti-jamming rejection capabilities. The main required modification is on the generation of a robust cross-ambiguity function (CAF) which is later used in the correlation process, both in acquisition and tracking modes. This project would encompass implementation and testing of such approach, including some of the variants and real signal processing. A reference article might be downloaded from [here](http://www.insidegnss.com/auto/sepoct17-BORIO_0.pdf).   

### Skills required:

Basic knowledge on digital signal processing and C++ programming (familiarity with the GNU Radio framework is a plus).

### Potential mentor(s):

Dr. Pau Closas, Dr. Carles Fern&aacute;ndez-Prades, Dr. Jordi Vil&agrave;-Valls.

-------


## Optimal frame synchronization detection

### Description:

GNSS data demodulation is preceded by frame synchronization. This process is critical, since it may prevent data recovery if not sufficiently reliable. Currently, GNSS-SDR implements a hard correlation scheme where correlation with the known pattern is performed. Although useful due to is simplicity, there are no performance guarantees for such approach. Particularly, in low signal-to-noise ratio (SNR) situations the performance of such correlation may degrade. This situations occur, for instance, in the presence of jamming signals. The goal of the project will be to implement an optimal detector, based on Massey's frame synchronization metric. Characterization of its performance and comparison to the current method in a number of SNR conditions.

J. L. Massey, [Optimum frame synchronization](http://www.isiweb.ee.ethz.ch/archive/massey_pub/pdf/BI417.pdf), IEEE Trans. Commun., vol. 20, no. 2, pp. 115–119, April 1972.

### Skills required:

Basic knowledge on digital signal processing and C++ programming (familiarity with the GNU Radio framework is a plus).

### Potential mentor(s):

Dr. Pau Closas, Dr. Jordi Vil&agrave;-Valls, Dr. Monica Navarro.

-------

## Acquisition and Tracking GNU Radio blocks for different data types

### Description:

As discussed at [Issue #75](https://github.com/gnss-sdr/gnss-sdr/issues/75), it would be nice to have a mechanism to avoid duplication of code when implementing Acquisition and Tracking blocks for different data types. This project consists of designing a suitable solution (based on templates or any other proposed approach, to be discussed) and implementing it for the existing blocks. Including a first draft of such design and discussing its Pros and Cons in the proposal will be highly appreciated.

### Skills required:

Solid knowledge on C++ programming (familiarity with the GNU Radio framework is a plus).

### Potential mentor(s):

Dr. Carles Fern&aacute;ndez-Prades, Dr. Javier Arribas.

-------

## Graphical User Interface for GNSS-SDR configuration

### Description:

The configuration mechanism of GNSS-SDR allows users to define and configure each of the receiver's signal processing blocks in a single file. Those configuration files constitute full receiver definitions, since they specify the implementation and parameters to be used in the receiver chain. However, the configuration process is poorly documented and only few baseline examples are provided. The objective of this project is to continue the development started in GSoC 2017 on a Graphical User Interface for the generation of such configuration files, allowing for an intuitive, user-friendly software receiver definition. That work is now in the `gui` branch of the [upstream repository](https://github.com/gnss-sdr/gnss-sdr).

### Skills required:

Good understanding of digital signal processing and C++ programming (familiarity with the [GNU Radio](http://gnuradio.org) framework and [Qt](https://www.qt.io) is a plus).

### Potential mentor(s):

Dr. Javier Arribas,  Mr. Luis Esteve, Dr. Carles Fern&aacute;ndez-Prades.


-------


## Proposal template:

  1. **Student's Name**
  2. **Email Address**
  3. **Name of the Project**
  4. **Summary**: Short statement about your intents (100 words approx.).
  5. **Benefits**: What are the benefits of your proposal?
  6. **Plan**: Describe your work plan in detail (tasks and schedule). Would there be blackout days (vacations, short jobs, etc.)?
  7. **Deliverables**: What are you going to deliver and when?
  8. **Communication**: How will you communicate with your mentor and the developers community?
  9. **Qualification**: Why you are the best candidate for this project?