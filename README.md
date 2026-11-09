# carbon-fiber-inline-loading
Failure analysis of feeding chopped carbon fiber in-line with PLA-CF on a desktop FDM printer, and what it taught me about composite processing.
Peter Cohan · Home lab experiment · Write-up reconstructed afterward (see Documentation note)

Abstract

Commercial carbon-fiber-filled PLA (PLA-CF) carries a fixed fiber loading set by the manufacturer. I tried to raise the effective fiber content of printed parts without making custom filament. I fed chopped carbon fiber, blended to a near-powder, into a modified PTFE feed tube on a Bambu Lab P1S, where it was drawn into the hotend with the PLA-CF filament. Some additional carbon was deposited into the print, which showed that in-line loading is physically possible. The hotend then clogged, and the clog destroyed the print head. My leading explanation is that dry, unwetted, unmetered fiber entered the melt zone, agglomerated, and jammed at the nozzle constriction while also raising melt viscosity past what the extruder could push. The failure showed that fiber has to be dispersed in the polymer before it reaches the hotend. That conclusion led directly to my next project: a desktop filament extruder for compounding composite filament at controlled, measured fiber loadings.

Motivation and Hypothesis

Short carbon fibers stiffen a polymer by carrying load across the matrix. More fiber should give a stiffer part, up to a point. Commercial PLA-CF fixes that loading, and making custom filament takes equipment I didn't have at the time.

Hypothesis: Adding chopped carbon fiber in-line with PLA-CF filament would raise the fiber content of the printed part and increase its stiffness, without manufacturing new filament.

Setup

Item	Detail
Printer	Bambu Lab P1S
Base filament	PLA-CF
Additive	1/4" chopped carbon fiber, blended to near-dust
Feed method	Modified PTFE feed tube; loose fiber was drawn into the extruder alongside the filament

Result

	•	Some additional carbon fiber made it through the hotend and into the printed part.
	•	The hotend then clogged. The clog destroyed the print head.

Failure Analysis

These are hypotheses, not confirmed causes. I didn't instrument the experiment, so I can't separate them yet. Each one is listed with how it could be tested.

1. Unmetered loading.
The fiber went in by being dragged along with the filament, so nothing controlled how much entered at any moment. Local fiber concentration could spike far above the average.
Test: Repeat with a metered feed and see whether failure depends on feed rate.

2. Dry fiber was never wetted by the polymer.
In commercial PLA-CF, every fiber is already surrounded by polymer, so the melt flows like a suspension. Loose dry fiber has no polymer coating. It can pack together as a dry mass instead of flowing, especially in the heat break, where the plastic is only partly melted.
Test: Inspect a sectioned nozzle and heat break. Packed dry fiber versus fiber embedded in plastic shows where the jam formed.

3. Agglomeration at the nozzle constriction.
Blending makes fibers shorter but does not separate them, so clumps can easily be larger than the nozzle bore. Particle-laden flows tend to jam at a constriction once particles or clumps approach a meaningful fraction of the orifice diameter, especially at high solids content.
Test: Measure the fiber length distribution of the blended fiber under a microscope and compare it to the nozzle diameter.

4. Melt viscosity exceeded what the extruder could push.
Short fiber raises a polymer melt's viscosity, and PLA-CF already contains fiber. Adding more raises back-pressure until the extruder gears can no longer drive the filament.
Test: Compare extrusion force or flow rate at increasing fiber loadings, using controlled-loading filament.

What I Would Do Differently

The core problem is that the fiber met the polymer for the first time inside the hotend. The fix is to compound the fiber into the polymer beforehand, at a known weight fraction, and then print normal filament. My plan:

	1.	Build a desktop filament extruder and use it to make composite filament at controlled loadings (for example 0%, 2%, 5%, 10% added fiber).
	2.	Check actual fiber content with a matrix burn-off test (burning away the polymer and weighing the remaining fiber, the same principle as ASTM D2584 ignition-loss testing).
	3.	Measure stiffness and strength of printed parts on a custom-built test rig.
	4.	Find the loading at which printing fails, so the clog becomes a measured threshold instead of an accident.

Documentation Note

I didn't document this experiment while I ran it. This write-up was reconstructed afterward from memory. Details I don't remember precisely, such as fiber quantity, print settings, and time to failure, are left out rather than estimated. Not recording data in real time is one of the lessons of this experiment, and I now keep a lab log for every project.