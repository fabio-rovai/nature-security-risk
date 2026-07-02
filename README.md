# Nature-Related Security Risk (NSR)

**An open, machine-readable evidence base and systems ontology that operationalises documented nature-to-security cascades for government use.**

Maintained by [The Tesseract Academy](https://gov.tesseract.academy). Data and documentation under CC-BY-4.0; code under MIT. Candidate-for-review and open to correction: <fabio@thetesseractacademy.com>.

---

## Why this exists

In January 2026 the UK Government published its [National Security Assessment on global biodiversity loss, ecosystem collapse and national security](https://www.gov.uk/government/publications/nature-security-assessment-on-global-biodiversity-loss-ecosystem-collapse-and-national-security) (the "Nature Security Assessment", NSA). It applies intelligence-community analytical tradecraft to nature loss: cascading risk chains, tipping points, feedback loops, compounding shocks, and six strategic ecosystems whose collapse would carry security consequences. It assesses, with high confidence, that every one of those ecosystems is on a pathway to collapse.

The NSA is a landmark. It is also a **one-off written assessment**. It cites external indicators (the Biodiversity Intactness Index, the Living Planet Index, the IUCN Red List) but ships **no machine-readable dataset, no shared ontology, and no standing monitoring or early-warning mechanism**. Its causal chains live as prose and figures; they cannot be programmatically ingested, versioned, queried or stress-tested.

That is the gap this repository fills. We surveyed the field (see [`sources.md`](sources.md)) and found:

- The **framing** now exists and is government-endorsed (UK NSA 2026; Council on Strategic Risks "ecological / natural security", Schoonover 2021; SIPRI *Biosphere Security* 2023).
- The **systems science** exists (IPBES *Nexus Assessment* 2024; *Global Tipping Points* 2023).
- The **reusable indicators and standards** exist (IPBES conceptual framework, Kunming-Montreal Global Biodiversity Framework monitoring indicators, TNFD, SEEA Ecosystem Accounting, Planetary Boundaries, ND-GAIN, BII, WRI Aqueduct, IUCN Red List of Ecosystems, Swiss Re BES).
- What does **not** exist is an **open, computation-ready evidence base + systems ontology that maps documented nature-to-security cascades** and grafts the missing *threat -> ecosystem-service loss -> transmission channel -> human-security -> geopolitical* layer onto those otherwise apolitical building blocks.

The nearest machine-readable artefacts, [NatureKG](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12713199/) and [OpenBiodiv](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8486731/), are scoped to nature *finance* and *taxonomy* respectively. For *security*, the space is empty. This repository is a first, correctable occupation of it.

## What is here

| Path | What it is |
|---|---|
| [`docs/conceptual-framework.md`](docs/conceptual-framework.md) | The systems framework: drivers, ecosystem-service loss, transmission channels, security outcomes, and the four systems constructs the NSA names (tipping points, feedback loops, risk cascades, compounding shocks). |
| [`data/cascades.csv`](data/cascades.csv) | **14 documented nature-to-security cascade cases**, each traced to authoritative sources, classified by transmission channel and security outcome, and graded with the NSA's own analytical confidence ratings (High / Moderate / Low). Contested causal claims are flagged, not hidden. |
| [`ontology/nsro.ttl`](ontology/nsro.ttl) | The Nature-Related Security Risk Ontology (NSRO): OWL classes and typed causal properties for a cascade. |
| [`ontology/taxonomy.ttl`](ontology/taxonomy.ttl) | SKOS concept schemes for drivers, ecosystem services, transmission channels and security outcomes, cross-walked to the IPBES conceptual framework. |
| [`ontology/shapes.ttl`](ontology/shapes.ttl) | SHACL shapes that validate a cascade record (every cascade must carry a driver, a service loss, at least one transmission channel, an outcome, a confidence rating and a source). |
| [`indicators/methods.md`](indicators/methods.md) | Methods for the three government functions the programme asks for: **assess** (a nature-security exposure profile from open indicators), **monitor** (early-warning indicators, including tipping-point critical-slowing-down statistics), and **mitigate** (intervention-point mapping per cascade). |
| [`sources.md`](sources.md) | Every source, graded, with the honest "could not verify" list. |

## The three functions, made operational

The programme this work supports asks for tools that let government **(1) assess** security risks arising from nature loss, **(2) monitor** threats and detect emerging risks, and **(3) inform mitigation**. The evidence base is built so each maps to a concrete artefact:

1. **Assess.** The NSRO taxonomy plus a composite *nature-security exposure profile* that binds existing open indicators (BII, IUCN Red List of Ecosystems, WRI Aqueduct water stress, ND-GAIN vulnerability, Swiss Re BES fragility, FAO food-import dependency) to the transmission channels through which nature loss reaches security outcomes. Method in [`indicators/methods.md`](indicators/methods.md).
2. **Monitor.** Leading indicators per channel and, for tipping-point-driven cascades, the established early-warning-signal statistics (rising autocorrelation and variance, "critical slowing down") from the resilience literature and the *Global Tipping Points* 2023 report.
3. **Mitigate.** Each cascade in the evidence base carries typed intervention points, the place in the chain where it can be broken, cross-referenced to policy levers (National Risk Register entries, IPBES response options, Kunming-Montreal targets).

## How it aligns (interoperability, not reinvention)

NSRO is deliberately thin. It does not re-model nature; it references what already exists and adds only the security layer:

- **IPBES conceptual framework**: drivers and nature's contributions to people are reused as the upstream of every cascade.
- **UK Nature Security Assessment (2026)**: the six strategic ecosystems, the cascade/feedback structure, and the **High / Moderate / Low analytical confidence ratings** are adopted directly, so the evidence base speaks the assessment's own language.
- **Kunming-Montreal GBF monitoring indicators, SEEA-EA condition accounts, TNFD LEAP risk grammar**: referenced as the indicator and disclosure layer.

## The critique this is built against

Framing nature loss as national security is contested, and the strongest objection is recent and serious: [Tebboth et al. (2026), *PLOS Climate*](https://doi.org/10.1371/journal.pclm.0000873) argue that a securitisation framing can oversimplify causal claims, militarise policy and backfire; [Selby et al. (2017)](https://doi.org/10.1016/j.polgeo.2017.05.007) show how a single celebrated cascade claim (climate -> Syrian drought -> civil war) was overstated. This evidence base is designed against those failure modes:

- Every cascade is **evidence-graded**, not asserted; multi-causal and contested chains are flagged as such (the Syria case carries both Kelley 2015 and its Selby 2017 rebuttal).
- The framing is **civilian and preventive** (One Health surveillance, grain reserves, transboundary water treaties, ecosystem restoration), not militarised.
- The method is **transparent and reproducible**, so a reader can see how much weight each claim carries.

## The gaps we name

An honest evidence base states its own limits.

- **No shared denominator.** There is no census of nature-to-security cascades; this set is a curated, illustrative lower bound, not a complete list.
- **Attribution is probabilistic.** Nature loss is almost never a sole cause; it is a threat multiplier interacting with governance, poverty and markets. Confidence ratings reflect this.
- **Cases are illustrative, not exhaustive.** Fourteen documented cascades demonstrate the structure; they do not bound the phenomenon.
- **Indicators were built for other purposes.** BII, Aqueduct, ND-GAIN and the rest were not designed for security use; binding them to security outcomes is an explicit modelling choice, stated openly.

## Licence

Data and documentation: **CC-BY-4.0**. Code and schemas: **MIT**. Upstream ontologies and indicators are referenced by IRI under their own licences.
