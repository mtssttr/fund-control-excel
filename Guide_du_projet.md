# Contrôle quotidien d’un fonds actions

## Méthodologie française

Simulation rétrospective du 14 au 25 septembre 2026. Le fonds commence avec 1 000 000 EUR et 10 000 parts. Les 50 clôtures sont entièrement fictives et générées par une formule déterministe indépendante des données de marché. Les opérations, prix d’exécution, frais, états dépositaires et valeurs liquidatives de référence sont également simulés.

Les dates et prix sont typés. Les opérations sont reconnues à la négociation. Le règlement effectif modifie les espèces et les positions livrées. Les opérations non réglées restent dans les positions économiques et génèrent une créance de vente ou une dette d’achat. Le courtage de 5 EUR est inclus dans le montant net contractuel et n’est jamais déduit une seconde fois. Les charges fixes sont de 10 EUR par jour calendaire, sans paiement durant la période.

Actif net = titres économiques valorisés + espèces réglées + créances de vente - dettes d’achat - charges à payer. VL = actif net / parts. Les intérêts, changes, souscriptions, rachats et traitements d’OST sont exclus. Les noms des émetteurs ne servent qu’à rendre l’exercice concret ; les cours ne représentent aucune observation réelle.

Les références dépositaires proviennent d’un jeu complet figé avant les altérations internes. Elles sont indépendantes des formules du classeur, mais restent des données de simulation, pas des états d’un véritable établissement.

## Utilisation

1. Garder le classeur et le dossier Sources_projet ensemble. Si le dossier est déplacé, modifier Pilotage!B57 pour pointer vers propre ou investigation.
2. Choisir NON en Pilotage!C13, puis Données > Actualiser tout. Attendre la fin des requêtes et vérifier l’absence d’erreurs dans les connexions avant de choisir OUI. Un échec de chargement peut conserver des valeurs en cache : le contrôle porte sur les données effectivement chargées.
3. Choisir la date de contrôle en C6. Les données incomplètes, les écarts et les retards empêchent le statut Contrôles rapprochés.
4. Le fichier livré est le corrigé au 25/09, avec cinq corrections OUI et les six dossiers documentés. Pour rejouer l’exercice, garder investigation, choisir le 24/09 et remettre les cinq corrections à NON. La livraison de TR-017 intervient au 25/09.
5. Actualiser le TCD après modification de la date ou des corrections. Les compteurs principaux sont des formules et réagissent immédiatement.

Capacité préparée : 60 transactions importées, 10 ajouts, 20 dates, 100 prix et 100 positions dépositaires. Au-delà, étendre les plages et vérifier les contrôles avant utilisation.

## English walkthrough

Start on 14 September. TR-001 buys 600 Air Liquide shares at a **simulated execution price** of EUR 164.58, plus EUR 5 brokerage. The contract requires EUR 98753.00. On trade date, the fund owns the economic exposure and owes that amount, while settled cash remains unchanged. On 16 September, cash decreases and the payable disappears. With no price change, settlement itself does not generate a gain or loss.

TR-007 sells 200 Danone shares on 15 September at a simulated EUR 60.48. Net proceeds are EUR 12091.00. Economic holdings decrease on trade date and a receivable appears. On 17 September, the receivable turns into cash. Custodian comparisons use settled quantities, so the interval before settlement is not a position error.

Then choose 24 September. Follow a transaction from Rapprochements back to its RecordID in Transactions. Check the simulated custodian confirmation before approving any correction. A duplicate can affect transaction matching, positions, cash and NAV simultaneously; these are linked symptoms of one incident, not four independent incidents.

After applying the five supported corrections, the overdue delivery remains. Move to 25 September to observe its confirmation. The corrected final net assets are EUR 1,002,641.10 and NAV per unit is EUR 100.264110. There are still legitimate pending trades with future contractual settlement dates.

## What to demonstrate in an interview

Explain trade date versus settlement date; trace one cash or position discrepancy; show why pending trades belong in NAV; show that closing the investigation log cannot suppress an unresolved calculation; refresh the raw files without overwriting investigation notes. This is an AI-assisted educational simulation, not professional fund experience. Claim only the features you can independently explain, reproduce and modify.

## Vérifications et limite d’exécution

Les scénarios de calcul, données propres, corrections, identifiants dupliqués, cours manquants et 11e jour ont été exécutés avec le moteur de calcul utilisé pour générer le classeur. Les neuf requêtes Power Query et le TCD sont intégrés comme objets natifs, mais leur exécution dans Excel n’a pas pu être vérifiée automatiquement. Ne pas présenter le test de rechargement des données comme la preuve d’une actualisation Power Query native. Les détails sont fournis dans Rapport_verification.md.

Le graphique utilise une colonne technique Q masquée : NA() crée volontairement une lacune quand une VL est indisponible. Ce marqueur n’est pas un zéro ni une panne du calcul principal. Le graphique et le TCD restent éditables.

## Sources

- Synthetic data provenance and generation formula: Sources_projet/provenance.json.
- IFRS 9 B3.1.5: https://www.ifrs.org/content/dam/ifrs/publications/pdf-standards/english/2021/issued/part-a/ifrs-9-financial-instruments.pdf
- EU settlement transition: https://www.esma.europa.eu/press-news/esma-news/one-year-go-t1-settlement-regulatory-framework-complete-now-lets-make-it
- Native Mac Power Query setup follows Microsoft’s sample: https://support.microsoft.com/en-gb/excel/import-and-shape-data-in-excel-for-mac-power-query
