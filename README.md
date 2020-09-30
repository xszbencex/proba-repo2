Webtechnológiák: a Markdown használata ![markdown-logo](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/64px-Markdown-mark.svg.png)
============

A dokumentum tartalma
---

A dokumentum lépésről lépésre leírja annak a szoftver infrastruktúrának a telepítését, mely ahhoz szükséges, hogy a `make clean all` parancs végrehajtható legyen a <https://github.com/jeszy75/markdown-examples/tree/master/rmarkdown> könyvtárban. 

## A feladathoz szükséges szoftverkomponensek telepítése

+ ### **Miniconda**
    - A Miniconda rendelkezésre állását feltételezem, a conda csomagok szolgáltatják a szükséges függőségeket. A Minicondával történő telepítés azért előnyösebb, mint a sima parancssori (`apt-get install` stb.) telepítés, mert környezeteket (enviroments) tudunk létrehozni, amit aktívvá és inaktívvá tudunk tenni, másrészt rendszergazdai jogosultságra sincs szükség a csomagok telepítéséhez, így bármilyen környezetben tudjuk őket telepíteni.
    - Ha még nincs telepítve, akkor a *[Conda](https://docs.conda.io/en/latest/miniconda.html)* weboldán találunk instrukciókat a telepítéshez.
Webtechnológiák: a Markdown használata ![markdown-logo](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/64px-Markdown-mark.svg.png)
============

A dokumentum tartalma
---

A dokumentum lépésről lépésre leírja annak a szoftver infrastruktúrának a telepítését, mely ahhoz szükséges, hogy a `make clean all` parancs végrehajtható legyen a <https://github.com/jeszy75/markdown-examples/tree/master/rmarkdown> könyvtárban. 

## A feladathoz szükséges szoftverkomponensek telepítése

+ ### **Miniconda**
    - A Miniconda rendelkezésre állását feltételezem, a conda csomagok szolgáltatják a szükséges függőségeket. A Minicondával történő telepítés azért előnyösebb, mint a sima parancssori (`apt-get install` stb.) telepítés, mert környezeteket (enviroments) tudunk létrehozni, amit aktívvá és inaktívvá tudunk tenni, másrészt rendszergazdai jogosultságra sincs szükség a csomagok telepítéséhez, így bármilyen környezetben tudjuk őket telepíteni.
    - Ha még nincs telepítve, akkor a *[Conda](https://docs.conda.io/en/latest/miniconda.html)* weboldán találunk instrukciókat a telepítéshez.

+ ### **Git**
    - A *[Git](https://git-scm.com/)* egy verziókezelő rendszer, amely segítségével le tudjuk tölteni a saját gépünkre a szükséges könyvtárat, (repository-t) ahol a `make clean all` parancsot kell elvégezni.
    - A csomag telepítését a `conda install git` paranccsal tudjuk elvégezni.
    - A szükséges könyvtár jelen esetben a [jeszy75/markdown-examples](https://github.com/jeszy75/markdown-examples.git), ezt pedig a `git clone https://github.com/jeszy75/markdown-examples.git` paranccsal tudjuk klónozni.

+ ### **Make**
    - A *[Make](https://www.gnu.org/software/make/)* csomag telepítése előtt navigáljunk az rmakdown könyvtárba. Amelyet a `cd markdown-examples/rmarkdown` paranccsal tehetünk meg. Itt kell majd a *make* parancsot elvégezni.
    - Használjuk a `conda install make` commandot a **make** szoftvercsomag telepítéséhez.

+ ### **HTTPie**
    - Erre a csomagra azért lesz szükségünk, hogy az **rmarkdown-example.Rmd** állományban lévő bash parancsot értelmezni tudja az R Markdown és a megfelelő kimenetet adja.
    - Mielőtt telepítjük a *[HTTPie](https://httpie.org/)* csomagot, azelőtt a **conda**-ban 2 parancsot kell végrehajtanunk, annak érdekében, hogy sikeres legyen az installálás. Ezek a parancsok a `conda config --add channels conda-forge` és a `conda config --set channel_priority strict` (a parancsok szükségességéről a <https://conda-forge.org/> oldalon olvashatunk).
    - Ezek után végeztessük el a `conda install httpie` parancsot.
  
+ ### **R**
    - A *HTTTPie*-hoz hasonlóan, erre is azért lesz szükségünk, hogy az előző pontban szereplő állomyában lévő R programrészletet értelmezhetővé tegyük az *[R Markdown](https://rmarkdown.rstudio.com/)* számára és ki tudja íratni a program kimenetét a képernyőre.
    - Az *[R nyelvhez](https://www.r-project.org/)* tartozó csomagot a `conda install r` parancssal telepíthetjük. Mivel használjuk az *r-ggplot2* könyvtárát az R nyelvnek, ezért ezt is telepítsük: `conda install r-gglpot2`.
    - Végül szükségünk lesz a `conda install r-rmarkdown`-ra is. Ő lesz a felelős azért, hogy az R Markdown a fordításkor az R programkód kimenetét ki tudja íratni a generált állományba.
  
+ ### **Python**
    - Mivel *[Python](https://www.python.org/)* kódunk is van az .Rmd fájlban, így az előzőekben látott megfelelő kimenet érdekében ezt is telepítenünk kell.
    - A pythont külön telepítésére nem lesz szükség, de ha még nincs python telepítve a gépünkre, akkor a <https://www.python.org/downloads/> oldalról letöltehtő.
    - A *Python* esetében is használunk egy csomagot, ezt pedig a `conda install seaborn` parancssal tölthetjük le.
    - Végül pedig futtassuk a `conda install r-reticulate` parancsot, mivel szükségünk lesz az r-reticulate csomagra a Python kód eredményének a kiíratására.

Majd jöhet a jól megérdemelt:

    make clean all

## Összefoglaló

| Csomag      | Letöltő parancs        | Egyéb parancsok                                              |
|:-----------:|:----------------------:|:------------------------------------------------------------:|
| Git         | `conda install git`    | `git clone https://github.com/jeszy75/markdown-examples.git` |
| Make        |  `conda install make`  | -                                                            |
| HTTPie      | `conda install httpie` | `conda config --add channels conda-forge` és  `conda   config --set channel_priority strict` |
| R           | `conda install r`      | `conda install r-gglpot2` és `conda install r-rmarkdown`     |
| Python      | -                      | `conda install seaborn` `conda install r-reticulate`         |

+ ### **Git**
    - A *[Git](https://git-scm.com/)* egy verziókezelő rendszer, amely segítségével le tudjuk tölteni a saját gépünkre a szükséges könyvtárat, (repository-t) ahol a `make clean all` parancsot kell elvégezni.
    - A csomag telepítését a `conda install git` paranccsal tudjuk elvégezni.
    - A szükséges könyvtár jelen esetben a [jeszy75/markdown-examples](https://github.com/jeszy75/markdown-examples.git), ezt pedig a `git clone https://github.com/jeszy75/markdown-examples.git` paranccsal tudjuk klónozni.

+ ### **Make**
    - A *[Make](https://www.gnu.org/software/make/)* csomag telepítése előtt navigáljunk az rmakdown könyvtárba. Amelyet a `cd markdown-examples/rmarkdown` paranccsal tehetünk meg. Itt kell majd a *make* parancsot elvégezni.
    - Használjuk a `conda install make` commandot a **make** szoftvercsomag telepítéséhez.

+ ### **HTTPie**
    - Erre a csomagra azért lesz szükségünk, hogy az **rmarkdown-example.Rmd** állományban lévő bash parancsot értelmezni tudja az R Markdown és a megfelelő kimenetet adja.
    - Mielőtt telepítjük a *[HTTPie](https://httpie.org/)* csomagot, azelőtt a **conda**-ban 2 parancsot kell végrehajtanunk, annak érdekében, hogy sikeres legyen az installálás. Ezek a parancsok a `conda config --add channels conda-forge` és a `conda config --set channel_priority strict` (a parancsok szükségességéről a <https://conda-forge.org/> oldalon olvashatunk).
    - Ezek után végeztessük el a `conda install httpie` parancsot.
  
+ ### **R**
    - A *HTTTPie*-hoz hasonlóan, erre is azért lesz szükségünk, hogy az előző pontban szereplő állomyában lévő R programrészletet értelmezhetővé tegyük az *[R Markdown](https://rmarkdown.rstudio.com/)* számára és ki tudja íratni a program kimenetét a képernyőre.
    - Az *[R nyelvhez](https://www.r-project.org/)* tartozó csomagot a `conda install r` parancssal telepíthetjük. Mivel használjuk az *r-ggplot2* könyvtárát az R nyelvnek, ezért ezt is telepítsük: `conda install r-gglpot2`.
    - Végül szükségünk lesz a `conda install r-rmarkdown`-ra is. Ő lesz a felelős azért, hogy az R Markdown a fordításkor az R programkód kimenetét ki tudja íratni a generált állományba.
  
+ ### **Python**
    - Mivel *[Python](https://www.python.org/)* kódunk is van az .Rmd fájlban, így az előzőekben látott megfelelő kimenet érdekében ezt is telepítenünk kell.
    - A pythont külön telepítésére nem lesz szükség, de ha még nincs python telepítve a gépünkre, akkor a <https://www.python.org/downloads/> oldalról letöltehtő.
    - A *Python* esetében is használunk egy csomagot, ezt pedig a `conda install seaborn` parancssal tölthetjük le.
    - Végül pedig futtassuk a `conda install r-reticulate` parancsot, mivel szükségünk lesz az r-reticulate csomagra a Python kód eredményének a kiíratására.

Ezek után használhatjuk a `make clean all` parancsot.

## Összefoglaló

| Csomag      | Letöltő parancs        | Egyéb parancsok                                              |
|:-----------:|:----------------------:|:------------------------------------------------------------:|
| Git         | `conda install git`    | `git clone https://github.com/jeszy75/markdown-examples.git` |
| Make        |  `conda install make`  | -                                                            |
| HTTPie      | `conda install httpie` | `conda config --add channels conda-forge` és  `conda   config --set channel_priority strict` |
| R           | `conda install r`      | `conda install r-gglpot2` és `conda install r-rmarkdown`     |
| Python      | -                      | `conda install seaborn` `conda install r-reticulate`         |
