# Medicinordinering - 3. Semester – Professionsbachelor i It-arkitektur Erhvervsakademi Aarhus

### 📝 Projektbeskrivelse

 - Dette projekt er et fællesforløb mellem fagene Systemudvikling og Softwarearkitektur. Formålet er at færdigudvikle og teste et system til registrering og styring af medicinordineringer på et sygehus. Systemet sikrer, at patienter får den korrekte mængde medicin baseret på forskellige ordinationstyper og individuelle faktorer som væg.

### 🎯 ProjektmålImplementering 

- Færdiggørelse af en model til registrering af lægemiddelordinationer
  
- Unit Test: Udvikling af tests med MStest til verificering af modelklasser og forretningslogik.
  
- Testspecifikation: Design og udførelse af testcases for use-casen "Opret ordination".

### 💊 Domænemodel 

- Systemet understøtter tre primære ordinationstyper, der alle har en start- og slutdato:

1. Daglig FastMedicinen gives dagligt på op til 4 faste tidspunkter (Morgen, Middag, Aften, Nat).
   
   ### Eksempel: Daglig fast
   
   Herunder ses en oversigt over en typisk "Daglig fast" ordination, hvor medicinen gives på faste tidspunkter i døgnet.
   
   | Tidspunkt | Morgen | Middag | Aften | Nat |
   | :--- | :---: | :---: | :---: | :---: |
   | **Enheder** | 2 | 1 | 0 | 1 |
   
3. Daglig SkævMedicinen gives dagligt, men på vilkårlige klokkeslæt og i varierende doser bestemt ved oprettelsen.
   
   ### Eksempel: Daglig skæv
   
   Ved en "Daglig skæv" ordination bestemmes de specifikke klokkeslæt og antal enheder ved oprettelsen.

   I dette eksempel gives medicinen 6 gange i døgnet:
   | Klokkeslæt | 09:30 | 10:30 | 13:30 | 14:30 | 19:30 | 20:30 |
   | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
   | **Enheder** | 2 | 1 | 2 | 1 | 2 | 1 |
   
5. PN (Pro Re Nata / Efter Behov)Medicinen gives efter behov inden for den gyldige periode.Systemet holder styr på specifikke datoer og antal gange, medicinen er givet.
6. Døgndosis for PN beregnes som:$$\frac{\text{antal anvendelser} \times \text{antal enheder}}{\text{antal dage mellem første og sidste givning}}$$
  
