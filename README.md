# PR21LDMMKPZG
Podatkovno rudarjenje - Luka Debevec, Matej Medved, Klavdij Puntar, Žan Gartner

Zbrali bomo podatke o kaznivih dejanjih glede na uro in kraj ter v katerem kraju se kazniva dejanja najbolj dogajajo. Pristojni bi temu primerno povečali/zmanjšali število aktivnih policistov in povečali učinkovitost preventivnih ukrepov. 
Ali obstaja korelacija med dejanji ter tipi storilcev bomo uporabili algoritme za gručenje, ki smo jih uporabili pri vajah.

Na grafu je vidno da število kriminala pada. Pri moških graf pada hitreje kot pri ženskah.

![image](https://user-images.githubusercontent.com/61451323/163279455-20333cf3-8cd9-4047-8cde-ef7285e0cb43.png)
```py
# { sex: {year: count} }
crimesBySex = {};
for sex, bySexData in dfGroupedBySex:
    if(sex not in crimesBySex):
        crimesBySex[sex] = defaultdict(int);
    for yearStr in bySexData["MesecStoritve"].values:
        year = int(yearStr.split(".")[1]);
        crimesBySex[sex][year] += 1;

plt.figure(figsize=(15,10));
for sex, crimesPerYear in crimesBySex.items():
    if(sex != "MOŠKI" and sex != "ŽENSKI"):
        continue;
    sortedYears = [ year for year in sorted(crimesPerYear.keys()) if(2010 <= year < 2020) ];
    crimesPerSortedYear = [ crimesPerYear[year] for year in sortedYears ];
    plt.plot(sortedYears, crimesPerSortedYear, label=sex, linewidth=2.0);
plt.legend();
```
Kazniva dejanja od leta 2010 do leta 2019 padajo.
![image](https://user-images.githubusercontent.com/61451323/163279481-cdded337-0899-4ac6-a4f1-3c5f11832a44.png)


```py
#group by mesec, count unique id
kd_leto = df.groupby(['MesecStoritve', 'UraStoritve','ZaporednaStevilkaKD'])
leto_counter = defaultdict(int)

for name,v in kd_leto:
    index = int((name[0].split(".")[1]))
    if index >= 2010 and index < 2020:
        leto_counter[index] +=1
    
    
list_mes_counter = sorted(leto_counter.items())
mesec, counter = zip(*list_mes_counter)
plt.figure(figsize=(15,10))
plt.plot(mesec,counter)
plt.show()
```
Števila kaznivih dejanj po mesecih se ne razlikujejo preveč. 
![image](https://user-images.githubusercontent.com/61451323/163279493-3bd0828b-493f-4cf9-b6e9-61c9ecba2b86.png)
```py
kd_mes = df.groupby(['MesecStoritve', 'UraStoritve','ZaporednaStevilkaKD'])
mes_counter = defaultdict(int)

for name,v in kd_mes:
    index = int((name[0].split(".")[0]))
    mes_counter[index] +=1


list_mes_counter = sorted(mes_counter.items())
mesec, counter = zip(*list_mes_counter)
plt.figure(figsize=(15,10))
plt.bar(mesec,counter)
plt.show()
```

Osebe stare od 33-44 povrzočijo največ kriminala. Sledijo jim osebe stare od 24-23 ter 44-54.
![image](https://user-images.githubusercontent.com/61451323/163279501-c36d4a5c-4297-474e-989a-d82c51ba6ed3.png)
```py
star_razredi = df.groupby(['StarostniRazred'])
star_razred, star_stevilo = zip(*[(name,razred.size) for name, razred in star_razredi])

star_stevilo = list(star_stevilo)
star_stevilo[-3] += star_stevilo[-2]

plt.figure(figsize=(15,10))
plt.bar(star_razred[:-2],star_stevilo[:-2])
plt.show()
```

Graf prikazije pojavnost kaznivih dejanj glede na uro dneva.
![image](https://user-images.githubusercontent.com/61451323/163279505-c2f7ece8-bff1-4db3-8087-23f8304c8e03.png)
```py
#group by mesec, count unique id
kd_ura = df.groupby(['UraStoritve', 'ZaporednaStevilkaKD'])
ura_counter = defaultdict(int)

for name,v in kd_ura:
    ura_counter[name[0]] += 1


list_ura_counter = sorted(ura_counter.items())
ura, counter = zip(*list_ura_counter)
plt.figure(figsize=(40,10))
plt.bar(ura,counter, color="black")
plt.show()
```
