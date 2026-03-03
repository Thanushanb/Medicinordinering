# Medicinordinering - 3. Semester – Professionsbachelor i It-arkitektur Erhvervsakademi Aarhus

📝 Projektbeskrivelse
Dette projekt er et fællesforløb mellem fagene Systemudvikling og Softwarearkitektur. Formålet er at færdigudvikle og teste et system til registrering og styring af medicinordineringer på et sygehus. Systemet sikrer, at patienter får den korrekte mængde medicin baseret på forskellige ordinationstyper og individuelle faktorer som væg.

🎯 ProjektmålImplementering 

- Færdiggørelse af en model til registrering af lægemiddelordinationer
  
- Unit Test: Udvikling af tests med MStest til verificering af modelklasser og forretningslogik.
  
- Testspecifikation: Design og udførelse af testcases for use-casen "Opret ordination".

💊 Domænemodel 
Systemet understøtter tre primære ordinationstyper, der alle har en start- og slutdato:
1. Daglig FastMedicinen gives dagligt på op til 4 faste tidspunkter (Morgen, Middag, Aften, Nat).
   Eksempel: 2 enheder morgen, 1 middag, 0 aften, 1 nat.
3. Daglig SkævMedicinen gives dagligt, men på vilkårlige klokkeslæt og i varierende doser bestemt ved oprettelsen.
4. 3. PN (Pro Re Nata / Efter Behov)Medicinen gives efter behov inden for den gyldige periode.Systemet holder styr på specifikke datoer og antal gange, medicinen er givet.Døgndosis for PN beregnes som:$$\frac{\text{antal anvendelser} \times \text{antal enheder}}{\text{antal dage mellem første og sidste givning}}$$
  
⚖️ Vægtbaseret Dosering
Systemet beregner en anbefalet døgndosis baseret på patientens vægt ved hjælp af tre faktorer:
Vægtklasse,Definition,Beregningsmetode
Let,Vægt < 25 kg,Vægt × Faktor (Let)
Normal,25 kg ≤ Vægt ≤ 120 kg,Vægt × Faktor (Normal)
Tung,Vægt > 120 kg,Vægt × Faktor (Tung)
,,
