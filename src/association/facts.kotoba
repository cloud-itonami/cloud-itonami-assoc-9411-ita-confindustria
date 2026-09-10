(ns association.facts
  "Industry rule/history catalog for Confindustria (Confederazione
  Generale dell'Industria Italiana) -- a 54th industry-association-
  level source (see cloud-itonami-assoc-9411-sau-fsc, -9411-aut-wko,
  -9411-irl-ibec, -9411-nzl-businessnz, -9411-cze-spcr, -9411-ind-cii,
  -9411-zaf-busa, -9411-bra-cni, -9411-ken-kam, -9411-can-chamber,
  -9411-mex-coparmex for the first eleven) per ADR-2607141700
  (cloud-itonami-compliance-fact-federation). The TWELFTH entry
  aligned to ISIC 9411 (activities of business, employers, and
  professional membership organizations). Fills Italy's
  previously-open association-axis gap (one of the 16-country gap
  list recorded at tick 146) -- Italy now has real, individually
  verified facts across ALL THREE axes (country:
  cloud-itonami-iso3166-ita statute.facts; municipality:
  cloud-itonami-municipality-ita-roma; association: this entry).

  Both entries directly WebFetch-verified against confindustria.it's
  own official 'Storia' (History) page
  (https://www.confindustria.it/storia/), which renders successfully
  and states verbatim: 'Da questi primi nuclei di associazionismo
  imprenditoriale sorti in ordine sparso nacque, il 5 maggio 1910, la
  \"Confederazione italiana dell'industria\"' (from these first
  entrepreneurial-association nuclei that arose scattered, the
  'Confederazione italiana dell'industria' was born on 5 May 1910)
  and 'Prima con sede a Torino – e successivamente dal 1919 a Roma'
  (first headquartered in Turin, and subsequently from 1919 in Rome).
  The 1910 date is independently corroborated by Wikidata Q1125309's
  own 'inception' statement. No personal names of office-holders are
  persisted here.

  An association not in `catalog` has NO spec-basis, full stop; never
  fabricate one.")

(def catalog
  "association-slug -> vector of association-rule entries."
  {"confindustria"
   [{:association-rule/id "confindustria.founding-1910-turin"
     :association-rule/title "'Confederazione italiana dell'industria' (Confindustria's founding name) born 5 May 1910, first headquartered in Turin (confindustria.it official 'Storia' page, corroborated by Wikidata Q1125309 inception statement)"
     :association-rule/association "confindustria"
     :association-rule/isic "9411"
     :association-rule/country "ITA"
     :association-rule/kind :governance-program
     :association-rule/url "https://www.confindustria.it/storia/"
     :association-rule/url-provenance :official-confindustria-it
     :association-rule/established-date "1910-05-05"
     :association-rule/retrieved-at "2026-07-17"
     :association-rule/topic #{:governance}}
    {:association-rule/id "confindustria.hq-moved-rome-1919"
     :association-rule/title "Confindustria's headquarters moved from Turin to Rome in 1919 ('successivamente dal 1919 a Roma') (confindustria.it official 'Storia' page)"
     :association-rule/association "confindustria"
     :association-rule/isic "9411"
     :association-rule/country "ITA"
     :association-rule/kind :governance-program
     :association-rule/url "https://www.confindustria.it/storia/"
     :association-rule/url-provenance :official-confindustria-it
     :association-rule/established-date "1919"
     :association-rule/retrieved-at "2026-07-17"
     :association-rule/topic #{:governance}}]})

(defn spec-basis [association] (get catalog association))

(defn coverage
  ([] (coverage (keys catalog)))
  ([associations]
   (let [have (filter catalog associations)
         missing (remove catalog associations)]
     {:requested (count associations)
      :covered (count have)
      :covered-associations (vec (sort have))
      :missing-associations (vec (sort missing))
      :note (str "cloud-itonami-assoc-9411-ita-confindustria Wave 0 (ADR-2607141700): "
                 (count (get catalog "confindustria")) " Confindustria entries seeded "
                 "with confindustria.it official Storia page + Wikidata Q1125309 corroboration. "
                 "Extend `association.facts/catalog`, never fabricate an id/url.")})))

(defn by-topic [association topic]
  (filterv #(contains? (:association-rule/topic %) topic) (spec-basis association)))
