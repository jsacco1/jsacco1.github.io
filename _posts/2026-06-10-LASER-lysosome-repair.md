---
title: "The Cell's 911 System for Lysosome Damage: What Our Nature Paper Actually Found"
date: 2026-06-10
tags: [lysosome, ESCRT, CRISPR, CRISPRi, functional genomics, neurodegeneration, hereditary spastic paraplegia, membrane repair, cell biology, TFG, LASER, Nature, publication]
header:
  image:
excerpt: "Our 2026 Nature paper identified LASER—a protein assembly that detects lysosomal membrane damage and dispatches the cellular repair machinery. Here is what the paper found, why it surprised us, and what it does not yet answer."
mathjax: "true"
---

A cell's lysosomes are its recycling centers. They are membrane-enclosed compartments filled with digestive enzymes, and their job is to break down cellular waste—damaged proteins, worn-out organelles, invading pathogens. They do this at a low pH, which means that if their membrane is breached, those enzymes spill into the cytoplasm. The result is catastrophic: an acidic, enzyme-rich flood that can trigger cell death.

Cells have evolved a rapid response to this problem. A set of proteins called ESCRT—short for Endosomal Sorting Complex Required for Transport—can detect and reseal membrane wounds within minutes. The problem that motivated our work was a deceptively simple question: how does ESCRT know to go to a damaged lysosome?

The ESCRT machinery is not idling near lysosomes waiting for trouble. It has to be recruited. And specifically, ESCRT-I—the first component in the sequential ESCRT assembly chain—has to recognize the damaged lysosomal membrane and anchor the entire repair response there. As of early 2026, no one had clearly established what connects damage sensing to ESCRT-I recruitment at lysosomes. That gap is what our paper closes.

## What We Found: A New Protein Assembly Called LASER

Working with genome-wide CRISPRi screens in a damage-sensitized genetic background, we identified a set of proteins that, when silenced, made cells dramatically more vulnerable to lysosomal damage. This is the power of genome-wide functional genomics: you can ask the entire genome simultaneously which genes matter for a given cellular phenotype, rather than testing candidates one at a time.

The screen pointed us toward a multicomponent protein assembly we named **LASER** (LC3/GABARAP-Assisted Stimulator for ESCRT Recruitment). LASER forms rapidly—within minutes—after lysosomal membranes are damaged, triggered by the calcium that leaks out of injured lysosomes.

At the center of LASER is a protein called **TFG**.

## The Unexpected Protagonist: TFG

TFG is not a lysosomal protein. Its established address in the cell is the ER exit site—the region of the endoplasmic reticulum where vesicles bud off to carry cargo through the secretory pathway. When we identified TFG as central to lysosomal repair, it was unexpected. ER exit sites and damaged lysosomes are different compartments with different functions. TFG had no known connection to either lysosomes or ESCRT biology.

What we found is that TFG is recruited to damaged lysosomes by binding to ATG8 family proteins—specifically LC3 and GABARAP—that are conjugated to lysosomal phospholipids upon membrane damage. The ATG8 proteins are well known in autophagy biology, where they coat autophagosomes. Here, they are being deployed on a damaged lysosomal membrane as a molecular distress flag.

TFG reads that flag. It binds ATG8 proteins on the injured membrane, concentrates there, and forms oligomeric assemblies—meaning it clusters into multi-copy complexes that amplify the signal. Those TFG oligomers then directly recruit TSG101, the key subunit of ESCRT-I, through conserved motif recognition. Avidity-driven interactions—where multiple weak binding events cooperate to produce a strong collective interaction—make the TSG101 recruitment robust and fast.

Once ESCRT-I is anchored, it initiates sequential assembly of ESCRT-II and ESCRT-III, and membrane resealing proceeds.

## The Disease Connection: Hereditary Spastic Paraplegia

The TFG finding connects directly to a neurological disease. Mutations in TFG are a known cause of hereditary spastic paraplegia (HSP), a progressive neurodegeneration that primarily affects upper motor neurons—causing slowly worsening lower limb spasticity, weakness, and in some forms, cognitive decline.

The disease mechanism was not well understood. Our data now implicate defective lysosomal repair as a driver. The TFG mutations associated with HSP disrupt TFG's ability to form the oligomeric assemblies needed to recruit ESCRT-I. The result: in cells carrying HSP-linked TFG variants, lysosomal membrane damage is poorly repaired. Neurons, which are long-lived post-mitotic cells with high lysosomal activity, are probably especially sensitive to this deficit accumulated over years.

This reframes HSP—at least the TFG-linked form—as a lysosomal repair disease. That has implications for how we think about therapeutic intervention, and it raises a broader question: how many other neurodegenerative conditions involve a similar lysosomal membrane repair failure that has been overlooked?

## What This Paper Does Not Answer

A few things this paper leaves open, worth being honest about:

**Tissue specificity.** Why neurons? Lysosomal membrane damage and ESCRT function operate across all cell types, yet TFG mutations produce a predominantly neurological phenotype. LASER may have tissue-specific modulators we have not yet identified, or neurons may have a specific vulnerability to unresolved damage events due to their longevity.

**Upstream regulation.** We established that calcium release triggers LASER assembly. But how calcium release is sensed at the molecular level and whether there are damage signals upstream of calcium that modulate the response is not resolved.

**Therapeutic tractability.** Knowing that lysosomal repair is impaired in HSP-TFG is an important mechanistic finding. Whether that is a druggable node—and with what class of intervention—is a separate and harder question.

**Generalizability of LASER.** ESCRT-dependent lysosomal repair occurs in many disease contexts—from lysosomal storage disorders to cancer cell survival under metabolic stress. Whether LASER is the primary damage-sensing mechanism across all contexts, or whether other recruitment pathways exist in parallel, remains to be determined.

## Why Computational Screening Made This Possible

The genome-wide CRISPRi approach was not merely a technical choice—it was epistemologically necessary. A candidate-based approach would have required us to already suspect TFG, which we would not have, because TFG's canonical biology gave no reason to implicate it here. The screen let the biology tell us what mattered.

This is increasingly the value proposition of functional genomics in cell biology: not hypothesis testing, but hypothesis generation at genome scale. Identifying LASER required the ability to process, normalize, and interpret signal-to-noise in a genome-wide perturbation dataset—and then validate the computational hits with rigorous cell biology. The computational and experimental were not separable here. They had to iterate.

---

The paper is open access in *Nature* (published June 3, 2026). If you work on lysosomal biology, ESCRT function, neurodegeneration, or functional genomics and want to discuss the work, feel free to reach out.

[jsacco001@gmail.com](mailto:jsacco001@gmail.com)
