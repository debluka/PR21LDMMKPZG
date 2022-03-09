# Člani skupine
- Luka Debevec
- Matej Medved
- Klavdij Puntar
- Žan Gartner

# 1. Izbrana tema
Naša izbrana tema so kazniva dejanja v Sloveniji. Zanima nas povezava med kaznivi dejanji in kje so se najpogosteje dogajala, katere vrste so bile najpogostejše nasplošno
in ter ločeno po regijah itd.

# 2. Cilji
Z analizo podatkov o kaznivih dejanjih, bi se lahko pristojni varnostni organi bolj učinkovito pripravili na analizo ter samo preprečevanje oz. zmanjšano pogosto kaznivih
dejanj v Sloveniji.

Z odkrivanjem določenih vzorcev to lahko pomaga tudi pri sami preiskavi in iskanju storilca.


# 3. Podatki
- Vir: https://podatki.gov.si/dataset/mnzpkazniva-dejanja-od-leta-2009-dalje

Na voljo so nam podatki o vseh kaznivih dejanjih v Sloveniji za katere je policija vložila kazensko ovadbo ali poročilo med letoma 2009 in 2019.

Predstavljeni so v formatu CSV

## Pomen atributov v zbirki
Atribut | Opis
-------- | -------- 
ZaporednaStevilkaKD | številka za štetje in ločevanje posameznega kaznivega dejanja
MesecStoritve | datum storitve kaznivega dejanja (MM.LLLL)
UraStoritve | ura storitve kaznivega dejanja (intervali)
DanVTednu | dan v tednu
PUStoritveKD | PU storitve kaznivega dejanja
Povratnik | atribut o tem, ali je osumljenec policiji znan ali ne (povratnik)
OpisKD | klasifikacija kaznivega dejanja (zakon/člen/odstavek/točka/alinea - tekst člena)
PoglavjeKD | poglavje zakonika
GospodarskiKriminal | vrsta kriminalitete (splošna/gospodarska)
OrganiziranKriminal | vrsta kriminalitete (organizirana)
MladoletniskaKriminaliteta | vrsta kriminalitete (mladoletniška)
Poskus | dokončanost kaznivega dejanja
KriminalisticnaOznacba1 | kriminalistična označba 1
KriminalisticnaOznacba2 | kriminalistična označba 2
KriminalisticnaOznacba3 | kriminalistična označba 3
UporabljenoSredstvo1 | uporabljeno sredstvo 1
UporabljenoSredstvo2 | uporabljeno sredstvo 2
UporabljenoSredstvo3 | uporabljeno sredstvo 3
UporabljenoSredstvo4 | uporabljeno sredstvo 4
UpravnaEnotaStoritve | upravna enota, kjer je bilo storjeno kaznivo dejanje
OpisKraja | podroben opis prizorišča kaznivega dejanja
LetoZakljucnegaDokumenta | leto zaključnega dokumenta
VrstaZakljucnegaDokumenta | vrsta zaključnega dokumenta
ZaporednaStevilkaOsebeVKD | številka za štetje in ločevanje oseb, udeleženih v kaznivih dejanjih
VrstaOsebe | kot kaj nastopa oseba v kaznivem dejanju
StarostniRazred | starostni razred, ki mu oseba pripada ob storitvi kaznivega dejanja
Spol | spol
Drzavljanstvo | državljanstvo osebe (le slovensko in tuje)
Poskodba | poškodba osebe
VplivAlkohola | vpliv alkohola
VplivMamil | vpliv mamil
OrganiziranaZdruzba | pripadnost organizirani združbi
Skoda | materialna škoda v EUR
