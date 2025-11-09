## Osnovne informacije
- Dataset sadrži **100.836 ocena**, **9.742 filma** i **610 korisnika**.  
- Ukupno ima **20 različitih žanrova**, a **34 filma nemaju dodeljen žanr** (`(no genres listed)`).

## Filmovi i žanrovi
- Žanrovi su zabeleženi kao stringovi sa separatorom `"|"`.  
- Distribucija filmova po žanrovima ima **logaritamski oblik** — žanrovi poput **Drama** i **Comedy** dominiraju, dok ostali imaju znatno manje filmova.  
- Prosečne ocene po žanrovima su **uglavnom uniformne**, bez većih razlika između njih.  

## Distribucija ocena
- Ocene imaju **left-skewed (blago levo nagnutu)** raspodelu.  
- Korisnici generalno daju **pozitivne ocene** — najčešća vrednost je **4.0**, dok je **medijana 3.26**.  
- Ovo ukazuje na **pozitivnu pristrasnost** (bias) korisnika prema filmovima koje ocenjuju.

## Broj ocena po filmu
- Prosečan film ima **oko 10 ocena** (std ≈ 22), dok **95% filmova ima manje od 47 ocena**.  
- Filmovi sa preko 200–300 ocena predstavljaju **outliere** i obično su **poznati klasici** koji su popularni među većinom korisnika.  
- Primećeno je da **filmovi sa više ocena generalno imaju i višu prosečnu ocenu**, što ukazuje da su popularni filmovi u proseku bolje ocenjeni.

## Aktivnost korisnika
- Većina korisnika ima **relativno mali broj ocena (do 600)**, dok pojedini “super-revieweri” imaju i **preko 2.000 ocena**.  
- Distribucija aktivnosti korisnika pokazuje **izraženu neravnomernost** — mali broj korisnika generiše veliki deo ukupnih ocena.  
- Ovakva struktura može izazvati **pristrasnost modela** prema aktivnijim korisnicima.

## Aktivnost kroz godine
- Broj ocena po godinama je **stohastičan**, bez jasnog trenda rasta ili pada.  
- Nema vidljive sezonalnosti ni konzistentnog obrasca — dataset sadrži ocene iz različitih perioda, što sugeriše da vremenski faktor nema dominantan uticaj.

## Tagovi
- Ukupno ima **3.680 tagova**, od čega **oko 1.600 različitih**.  
- Većina tagova se pojavljuje jednom, dok se nekoliko (“*In Netflix queue*”) javljaju više od 100 puta.  
- Tagovi su potencijalno korisni za **content-based** deo sistema (npr. TF-IDF vektorizacija).

## Sparsity matrice
- Matrica korisnik–film ima **popunjenost od 1.7%**.  
- Ovo je tipična vrednost za preporučivačke skupove i znači da su podaci **izrazito retki**.  
- Sama sparsity vrednost ne nosi direktnu interpretaciju, ali ukazuje da će **Collaborative Filtering** metode morati da se nose s velikim brojem nepoznatih vrednosti.

## Ključni zaključci
1. Korisnici daju uglavnom pozitivne ocene (bias ka višim vrednostima).  
2. Filmovi sa više ocena u proseku imaju i više prosečne ocene.  
3. Postoji mali broj ekstremno popularnih filmova (outlieri).  
4. Većina korisnika ocenjuje vrlo malo filmova → “long-tail” efekat.  
5. Dataset je retko popunjen (1.7%), što znači da će **hybrid modeli** verovatno dati bolje rezultate od čistih CF pristupa.
