## Simulation details

**Modeling framework**
- SLIM for ecology
	- Two types of chromosomes, mtDNA and nuclear, simulated in SLIM with no genetics and tree sequence recording.
	- One non-recombining genealogy for mtDNA. Nuclear DNA will have a recombination rate and possibility of recombination within the marker.
	- mtDNA is haploid and maternally inherited, while nuclear DNA is diploid and inherited by both parents
	- Male-base dispersal
	- How long? 100k generations maybe?
	- For model 4 (modeling selection): Each individual will be assigned to a mtDNA lineage in the beginning of the simulation, based on their spatial location. Each lineage will have a different fitness across space, based on latitude and longitude values. This mimics individuals in each lineage being selected positively at each of the different highlands. Divergence is maintained in the simulation by this selection (if individuals move across, they die, so genealogies don't cross.)
- `msprime` for recapitation
	- Scaling Ne to match empirical values
	- Nuclear Ne is four times that of mtDNA Ne.
	- Mutation rate (µ) will follow traditional rates for mtDNA and nuclear DNA.
	- Both Ne and µ need to be [scaled by generation time](https://tskit.dev/pyslim/docs/latest/time_units.html) (to convert from SLiM nonWF to `msprime` WF)

**Summary statistics**
- Pi per lineage
- Pi over space
- Fst across major lineages
- Pairwise Dxy across localities/major lineages
- Site Frequency Spectrum of each lineage
	- Maybe also joint pairwise SFS?
