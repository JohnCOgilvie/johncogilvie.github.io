---
permalink: /
title: "John C. Ogilvie - Navigator-in-training"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Hi! Welcome to my academic and professional portfolio website (as distinct from my non-academic website, link coming soon). This is a Medina Station of sorts to redirect or point you towards any of my non-fiction writing, publications, talks, or projects, and to serve as an academic and professional overview of me and my interests. 

I am currently a PhD Student at the University of New South Wales, based on their Canberra campus at the Australian Defence Force Academy (though I am not in the Defence Force), and I work part-time with Shoal Group as a Modelling & Simulation Engineer to support decision-making in Defence and Space. My research project revolves around spacecraft navigation, specifically in trajectory design, even more specifically in cislunar applications. How do we move in this region of space? How can we improve? What dynamics drive this motion? How do we design with failure and risk in mind? The Moon beckons, and we as a species have decided to return - I want to do my bit with the tools I have at my disposal to be a part of what will surely be the greatest undertaking of our generation. I hope. And if not, in the meantime, I get to learn about fascinating and beautiful maths and how the universe works. I mean, look at this: 

![Invariant Manifolds of the L1 libration point orbit [1]](../images/l1_libration_orbit_invariant_manifolds.png)
*Invariant Manifolds of the L1 libration point orbit [1]*

![3-body orbits around the Moon [2]](../images/3_body_orbits.jpg)
*3-body orbits around the Moon [2]*

![Members of the L1 quasi-halo family of orbits [3]](../images/l1_quasi_halo_family.png)
*Members of the L1 quasi-halo family of orbits [3]*

Just try and tell me things like this don't just draw you in and make you want to understand, to hear what music moves them. 

# PhD Project - Design and Analysis of Risk-Resilient Cislunar Spacecraft Trajectories
I've explored a number of ideas for my project, and I expect it will continue to evolve over the remainder of my study. As discussed above, they all centre around the concepts of trajectory design for cislunar applications. If my work touches on your research areas or you'd like to open a dialogue about it, I encourage you to get in touch via email (in the sidebar)!
## A risky region of space
Cislunar space represents a highly non-linear, chaotic, and uncertain area of space. At the time of writing, there are 38 public and private missions planned to the Moon, in addition to those already there. This is to become a very congested region, and the space will have to be shared. 

But unlike elliptical 2-body Keplerian orbits, when manoeuvres go wrong, either misfiring or not firing altogether, the dynamics of the region don't always permit a second attempt one period later. Periodic orbits are few and typically unstable, and most often transfers between them do not lie on repeating paths. Any failure to insert onto the nominal path typically means asymptotic departure from that path. How do we design or choose trajectories that account for this? What do we do when these failures occur?

## Getting the lay of the land
The first step to understanding the design space available to us is to quantify the properties of various cislunar orbits by metrics which can give us a quick overview of how an orbit may be exploitable for transfer design. These metrics include things like stability, Jacobi constant, observability, transfer $\Delta v$ requirements, and $\delta\Delta v$ acceptability. 

The last of these can be understood as the allowable error in a transfer manoeuvre that still enables mission success without further intervention (i.e. if we require 3km/s of $\Delta v$, whats the plus/minus on that 3km/s where the transfer can still achieve the desired orbit? 5%? 1%?). This allows us to have a quick-look heuristic by which we can filter orbits for the robustness of transfers to them, even though in the real world TCMs would clean up any actual manoeuvre error. 

This catalog of useful orbit and associated transfer parameters allows future work to examine the idea of waypoint orbits. For example, perhaps a particular mission orbit is particularly stringent on $\delta\Delta v$ acceptability and introduces a high degree of risk if a manoeuvre execution error occurs, but a nearby one has much broader allowable errors - mission designers may then target the second orbit for the TLI, exploiting its transfer robustness, and then design a secondary manoeuvre to the mission orbit. Initially, this was included in my project, but the design space is so large for orbit-to-orbit transfer design that we decided to focus on other areas, such as...

## Quantifying the real-world implications of failures
As discussed above, in the real world, FDOs would design TCMs to clean up any manoeuvre error in the TLI. In the first part of this work, we looked at $\delta\Delta v$ acceptability as a heuristic rather than a way spacecraft may fly in the real world - now we want to actually model these TCMs and identify how errors in initial transfer manoeuvre map to total $\Delta v$ budget for the mission. 

This part of the work focusses on a few orbits of interest to upcoming missions - NRHOs, DROs, and Lyapunov orbits are the most obvious to include here, but others may be included depending on how successful initial experimentation is. 

## Introducing navigation effects
Finally, to examine how these transfers may perform in the real world and how flight teams may actually respond to errors, we need to think about the error in our state estimation at the time of (and immediately after) a manoeuvre execution error. 

As alluded to above, in simple elliptical orbits, we have some grace in cases of misfiring - after all, in LEO we are only 90 minutes from the same position in the orbit. However, in the chaotic cislunar space, if a manoeuvre misfires or is even missed completely, the spacecraft begins to fall away from the nominal path rapidly, and there may not be a simple path back to the orbit of interest, especially in highly non-linear regions or for orbit insertion manoeuvres. This would lead one to think that immediately rectifying the error and attempting to certify and execute a manoeuvre as soon as possible would be the way to minimise fuel costs and failure risk. However, overlayed on top of the chaotic space is the error in our knowledge of the spacecraft position and velocity, and so a recovery manoeuvre may end up actually exacerbating the situation - and this error in state estimation changes over time (indeed, regions of cislunar space are even completely unobservable from Earth). So is there some optimal case, where we wait long enough for a better orbit determination estimate, but not so long that we travel too far from our mission goal to recover in a reasonable fuel cost?


References
------
[1] Anderson, R. L., & Parker, J. S. (2012). Survey of ballistic transfers to the lunar surface. Journal of Guidance, Control, and Dynamics, 35(4), 1256–1267. https://doi.org/10.2514/1.54830

[2] Baker-McEvilly, B., Bhadauria, S., Canales, D., & Frueh, C. (2024). A comprehensive review on Cislunar expansion and space domain awareness. Progress in Aerospace Sciences, 147. https://doi.org/10.1016/j.paerosci.2024.101019

[3] Brian McCarthy, & Kathleen Howell. (2022). Accessing the Vicinity of the L1 Libration Point via Low-Energy Transfers Leveraging Quasi-Periodic Orbits. Astrodynamics Specialist Conference.

