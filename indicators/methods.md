# Methods for assess, monitor and mitigate

The programme asks for tools that let government **assess**, **monitor** and **mitigate** nature-related security risk. This note specifies a reproducible method for each, built only on open indicators. No indicator is re-created; each is bound, by transmission channel, to the security layer.

## 1. Assess — a nature-security exposure profile

For a country or region, exposure is profiled per transmission channel by binding existing open indicators to that channel:

| Transmission channel | Open indicator(s) bound to it | Custodian |
|---|---|---|
| Food security | FAO cereal-import dependency ratio; pollination-dependent crop share (IPBES 2016) | FAO; IPBES |
| Water security | WRI Aqueduct baseline water stress; transboundary basin dependency | WRI |
| Human health / biosecurity | Zoonotic-spillover risk from land-use change (Allen et al. 2017; Gibb et al. 2020) | peer literature |
| Livelihoods | Share of employment in nature-dependent sectors; Swiss Re BES fragility | ILO; Swiss Re |
| State of nature (upstream) | Biodiversity Intactness Index; IUCN Red List of Ecosystems status | NHM; IUCN |
| Overall vulnerability | ND-GAIN country vulnerability and readiness | Notre Dame |

The profile is a **vector, not a single score**: it is deliberately not collapsed to one number, because a scalar would hide which channel is driving exposure, which is exactly the information a mitigation decision needs. Weighting is left explicit and adjustable; no weights are hard-coded. This design choice directly answers the securitisation critique that composite security indices oversimplify.

Reproducibility note: this repository specifies the method and the indicator sources rather than shipping a frozen scored table, because the underlying indicators update on their own cycles and are re-pointable. Every source is public and named above.

## 2. Monitor — early warning

Two families of leading indicator:

- **Driver-side (tipping points).** For cascades driven by a tipping point (`nsro:TippingPoint`; Amazon dieback, AMOC), the established early-warning-signal statistics apply: **critical slowing down**, seen as rising lag-1 autocorrelation and rising variance in the system's state variable (Scheffer et al. 2009; *Global Tipping Points* report, 2023). These are computed on the monitored ecosystem indicator time series, not asserted.
- **Channel-side (proximate).** Food-price volatility against the threshold identified by Lagi et al. (2011); water-stress trend (Aqueduct); anomaly detection on displacement and crop-condition series (FEWS NET, FAO). Each is a leading indicator on a specific channel in the cascade set.

An emerging risk is flagged when a driver-side early-warning signal and a channel-side leading indicator move together for a cascade that the evidence base already documents, tying detection back to a known structure rather than a bare anomaly.

## 3. Mitigate — intervention-point mapping

Every cascade in [`../data/cascades.csv`](../data/cascades.csv) carries an `intervention_point`: the place in the chain where it is cheapest to break, expressed as a civilian, preventive lever (grain reserves and trade-policy coordination for food; One Health surveillance and wildlife-trade regulation for zoonotic spillover; transboundary water treaties and benefit-sharing for interstate water tension; ecosystem restoration and resilience monitoring for tipping-point cascades). Each maps to a policy home: a National Risk Register entry, an IPBES response option, or a Kunming-Montreal Global Biodiversity Framework target. The framing is deliberately non-militarised, per the design principles in the README.
