# Tesztautomatizálási kérdések

## Tesztelési alapok (ISTQB-hez kapcsolódó)
<img src="https://www.mindsmapped.com/wp-content/uploads/2016/06/ISTQB.jpg" alt="image" width="300" height="220">

#### ✅ Mi a tesztelés célja? Mi nem az?
    A tesztelés célja, hogy megtaláljunk minél több, a fejlesztés során létrejövő hibákat minél korábban való azonosítása különböző szempontok szerint, csökkentve annak javítási költségét, biztosítva, hogy a szoftver megfelelően működjön minden környezetben és használati helyzetben.

#### ✅ Mik a tesztelési alapelvek?
    A tesztelés alapjait a következő alapelvekben foglalhatjuk össze:
    1. A tesztelés hibák jelenlétét jelzi: A tesztelés képes felfedni a hibákat, de azt nem, hogy nincs hiba. Ugyanakkor a szoftver minőségét és megbízhatóságát növeli.
    2. Nem lehetséges kimerítő teszt: Minden bemeneti kombinációt nem lehet letesztelni (csak egy 10 hosszú karakterláncnak 256^10 lehetséges értéke van) és nem is érdemes. Általában csak a magas kockázatú és magas prioritású részeket teszteljük.
    3. Korai teszt: Érdemes a tesztelést az életciklus minél korábbi szakaszában elkezdeni, mert minél hamar találunk meg egy hibát (mondjuk a specifikációban), annál olcsóbb javítani. Ez azt is jelenti, hogy nemcsak programot, hanem dokumentumokat is lehet tesztelni.
    4. Hibák csoportosulása: A tesztelésre csak véges időnk van, ezért a tesztelést azokra a modulokra kell koncentrálni, ahol a hibák a legvalószínűbbek, illetve azokra a bemenetekre kell tesztelnünk, amelyre valószínűleg hibás a szoftver (pl. szélsőértékek).
    5. A féregirtó paradoxon: Ha az újratesztelés során (lásd később a regressziós tesztet) mindig ugyanazokat a teszteseteket futtatjuk, akkor egy idő után ezek már nem találnak több hibát (mintha a férgek alkalmazkodnának a teszthez). Ezért a tesztjeinket néha bővíteni kell.
    6. A tesztelés függ a körülményektől: Másképp tesztelünk egy atomerőműnek szánt programot és egy beadandót. Másképp tesztelünk, ha a tesztre 10 napunk vagy csak egy éjszakánk van.
    7. A hibátlan rendszer téveszméje: Hiába javítjuk ki a hibákat a szoftverben, azzal nem lesz elégedett a megrendelő, ha nem felel meg az igényeinek. Azaz használhatatlan szoftvert nem érdemes tesztelni.

#### ✅ Mi az egységtesztelés (unit testing)? Ki felelős az egységtesztek írásáért?
    Az egységtesztelés (unit testing) a szoftvertesztelés egy módszere, amely során a forráskód egységeit (egy vagy több programmodul készletet) a kapcsolódó vezérlő adatokkal, felhasználási- és működtető eljárásokkal együtt tesztelik annak meghatározására, hogy elérik-e a kitűzött céljaikat. Ez a módszer a kód egyes egységeinek elkülönítésére és tesztelésére szolgál, hogy meghatározza az egyes komponensek hatékonyságát és biztosítsa azok helyességét. Az egységtesztek írásáért a minőségbiztosítási csapat felelős.
#### ✅ Mik a tesztszintek, és mi a különbség köztük?
    A szoftvertesztelés négy szintje a következő:

    1. Egységteszt vagy komponensteszt: Az egységteszt a szoftverkomponensek elkülönített tesztelésére szolgál, annak ellenőrzésére, hogy azok teljesítik-e a funkcionális követelményeket. A cél a szoftver minden részének külön-külön történő tesztelése. Ez a tesztelés általában a fejlesztők feladata, és gyakran fehér dobozos tesztelést alkalmaznak, mivel a forráskód ismerete szükséges.

    2. Integrációs teszt: Az integrációs teszt a különálló modulok közötti adatkapcsolatokat ellenőrzi, és biztosítja, hogy ezek megfelelően működjenek együtt. Ebben a szakaszban a különböző modulokat kombinálják és csoportosan tesztelik, hogy megbizonyosodjanak arról, hogy az integrált rendszer készen áll a rendszertesztelésre. Ezt a tesztelést gyakran tesztelők végzik.

    3. Rendszerteszt: A rendszerteszt a teljes szoftverrendszer működését vizsgálja, általában feketedobozos tesztelési módszerrel. Ezt gyakran független cégek végzik, hogy objektíven ellenőrizzék, hogy a termék megfelel-e a specifikációkban meghatározott követelményeknek. Például, ha a követelmény azt írja elő, hogy a szoftvernek képesnek kell lennie éves forgalmi jelentést készíteni, akkor a tesztelők ezt kipróbálják. A rendszerteszthez használt környezetnek a lehető legjobban hasonlítania kell a végfelhasználói környezethez, hogy a környezet-specifikus hibákat is fel lehessen deríteni.

    4. Átvételi teszt (elfogadási teszt): Ez a szint szintén a teljes rendszer tesztelését jelenti, de ezt már a végfelhasználók végzik, hogy ellenőrizzék, a szoftver megfelel-e az igényeiknek és elvárásaiknak.

#### ✅ Mi a különbség a verifikáció és a validáció között?
    Mi a különbség a verifikáció és a validáció között?

    A verifikáció azt vizsgálja, hogy a termék megfelel-e a terveknek, míg a validáció azt, hogy a tervek megfelelnek-e a szükségleteknek vagy a problémának. Ezért a verifikáció az érvényesítés/igazolás, míg a validáció az ellenőrzés folyamata.

#### ✅ Mik a tesztelési típusok, és mi a különbség köztük?
    A tesztelési típusok a teszttevékenységek különböző csoportjai, amelyek célja a szoftverrendszer vagy annak egyes részeinek meghatározott tesztcélok alapján történő vizsgálata. Az egyes típusok céljai a következők lehetnek:  

    - Funkcionális minőségi jellemzők vizsgálata: Ilyen jellemzők például a teljesség, a helyesség és a megfelelőség.  
    - Nem funkcionális minőségi jellemzők elemzése: Ide tartozik például a megbízhatóság, a teljesítményhatékonyság, a biztonság, a kompatibilitás és a használhatóság.  
    - Strukturális és architekturális helyesség értékelése: Vizsgálja, hogy a komponens vagy a rendszer struktúrája és architektúrája megfelelő-e, teljes-e, és megfelel-e a specifikációknak.  
    - Változások hatásának vizsgálata: Ide tartozik az ellenőrző tesztelés, amely azt erősíti meg, hogy a hibákat kijavították, valamint a regressziós tesztelés, amely a szoftver vagy környezet változásából eredő nem kívánt hatásokat kutatja.  

    A tesztelési típusok közötti különbségek a vizsgált aspektusokban és a tesztelés konkrét céljaiban rejlenek.

#### ✅ Mi a különbség a fehér doboz, szürke doboz és fekete doboz tesztelés között?
    A feketedobozos tesztelés során a tesztelő nem rendelkezik információval a tesztelni kívánt alkalmazás belső felépítéséről, míg a fehérdobozos tesztelés esetén a tesztelő hozzáfér a szoftver belső szerkezetéhez és kódjához.

    A szürkedobozos tesztelés a fehérdobozos és feketedobozos tesztelés kombinációja. Itt a tesztelő bizonyos szintű hozzáféréssel rendelkezik a rendszer belső felépítéséhez, de nem teljes körű ismeretekkel. Ennek célja, hogy felderítse azokat a hibákat, amelyek a nem megfelelő alkalmazásfelépítésből vagy használatból erednek.

#### ✅ Mi a különbség a felhasználói elfogadási teszt (UAT) és a rendszerteszt között?
    A felhasználói elfogadási teszt (UAT) a szoftverfejlesztési folyamat utolsó lépése, amely során a véglegesített terméket a valós szoftverfelhasználók és ügyfelek számára tesztelik. Az UAT célja annak biztosítása, hogy a szoftver a tervezési specifikációknak megfelelően képes kezelni a valós forgatókönyveket, és hogy az ügyfelek elégedettek legyenek a termékkel. A tesztelés ezen formáját gyakran bétatesztelésnek, alkalmazástesztelésnek vagy végfelhasználói tesztelésnek is nevezik.

    A rendszerteszt ezzel szemben a szoftver teljes rendszerének tesztelése, amelyet akkor végeznek, amikor az összes modul és komponens integrálódott. A rendszertesztelés célja annak ellenőrzése, hogy a rendszer megfelel-e a funkcionális és nem funkcionális követelményeknek. A rendszerteszt fekete dobozos tesztelés, ami azt jelenti, hogy a tesztelés során nem vizsgálják a szoftver belső felépítését, hanem kizárólag a működő funkciókat értékelik, a felhasználói élményt szem előtt tartva.

#### ✅ Sorolj fel különbségeket a regressziós tesztelés, a füsttesztelés és az újratesztelés között!
    1. Regressziós tesztelés vs. Újratesztelés:
    - A regressziós tesztelést akkor hajtják végre, ha egy teszteset sikeres, míg az újratesztelést csak a sikertelen teszteseteknél alkalmazzák.
    - A regressziós tesztelés célja a váratlan mellékhatások ellenőrzése, míg az újratesztelés arra szolgál, hogy biztosítsa, hogy az eredeti hibát valóban kijavították.
    - A regressziós tesztelés nem tartalmazza a hibaellenőrzést, míg az újratesztelés magában foglalja a hibaellenőrzést.
    - A regressziós tesztelés általános tesztelés, míg az újratesztelés tervezett tesztelés.
    - A regressziós tesztelés automatizálható, míg az újratesztelés nem.

    2. Füsttesztelés:
    A füsttesztelés a szoftver tesztelésének egy gyors és alapvető szintje, amelynek célja annak biztosítása, hogy a legfontosabb funkciók és a szoftver stabilitása megfelel a minimum követelményeknek. Ez egyfajta miniatűr, gyors regressziós tesztelés, amely a legfontosabb funkciókat ellenőrzi, hogy megbizonyosodjon azok működéséről. Ha a termék nem teljesíti a füsttesztet, az azt jelzi, hogy a szoftverben jelentős hibák vannak, amelyek javítása előtt nem folytatható a további tesztelés.

#### ✅ Mi a különbség a statikus és dinamikus tesztelés között?
    A statikus tesztelés a szoftver tényleges futtatása nélkül történik, azaz a kódot és a dokumentációt elemzik lépésről lépésre, anélkül, hogy azt végrehajtanák. Ennek célja a hibák, hiányosságok és szabálytalanságok felfedezése már a fejlesztés korai szakaszában. A dinamikus tesztelés ezzel szemben csak a kód elkészülte után kezdhető el, és a szoftver valódi működését, illetve teljesítményét tesztelik. A dinamikus tesztelés automatizálható, és a tesztelés minden szintjén végrehajtható, tehát a gép végzi a tesztelési folyamatot.

### ✅ Hasonlítsd össze a V-modellt, a vízesés modellt és az Agile megközelítést a tesztelés szempontjából!
    Waterfall (Vízesés modell):  
    A Waterfall modell egy szigorúan lépcsőzetes, előre meghatározott folyamatot követ, ahol minden lépés (követelmények összegyűjtése, tervezés, fejlesztés, tesztelés, telepítés) egy-egy különálló fázisként valósul meg. A következő fázis csak akkor kezdődhet, ha az előző befejeződött. Előnye, hogy könnyen követhető, a csapat tagjai a projekt során nem kell folyamatosan visszajelzéseket kérjenek, és a végtermék jól meghatározott, kiszámítható. Hátránya, hogy nem rugalmas, és nem alkalmazkodik jól az ügyfél visszajelzéseihez vagy az új igényekhez, mivel minden előre dokumentált és jóváhagyott.

    Agile:  
    Az Agile módszertan rugalmasabb megközelítést kínál, amely lehetővé teszi a követelmények és az eredmények iterációkon keresztül történő folyamatos fejlődését. A csapatok kezdetben meghatározzák a követelményeket, de a fejlesztés során folyamatosan visszajelzést gyűjtenek, és az új igények alapján frissítik a projektet. Az Agile nagyobb rugalmasságot és gyorsabb fejlesztést tesz lehetővé, hiszen a részletes tervezés és dokumentálás helyett a csapatok közvetlenül a termékre összpontosítanak. Azonban mivel az eredmények nem mindig kiszámíthatók, és minden csapattagnak aktívan részt kell venni a folyamatban, nem minden projekt esetén ideális.

    V-modell:  
    A V-modell a vízesés modell kiterjesztése, amelyben a fejlesztési és tesztelési fázisokat párhuzamosan kezelik. A fejlesztési fázisok mindegyikéhez kapcsolódik egy tesztelési szint, amely biztosítja, hogy a tesztelés a lehető legkorábban elkezdődhessen, így a hibák hamarabb észlelhetők. Ez a modell az Agile-hez hasonlóan előnyben részesíti a korai tesztelést, de strukturáltabb, és biztosítja, hogy a tesztelés és a fejlesztés lépései szoros kapcsolatban álljanak egymással. A V-modell tehát egy strukturáltabb megközelítést kínál a fejlesztés és a tesztelés integrálásával.

    Összegzésül:
    - A Waterfall egyszerű, előre meghatározott, de nem rugalmas.
    - Az Agile gyors, rugalmas, de kevésbé kiszámítható.
    - A V-modell integrálja a tesztelést a fejlesztési folyamatba, de szigorúbb a folyamatok sorrendje, mint az Agile-ban.

<img src="https://t4.ftcdn.net/jpg/03/90/15/65/360_F_390156585_8w1lsOyICIAOvDCU8tExXW2QwLCOFwXD.jpg" alt="image" width="550" height="400">


<img src="https://i.imgur.com/S38EBJw.png" alt="image" width="550" height="400">   <img src="https://segedletek.level14.hu/assets/img/modszertan-vizeses.svg" alt="image" width="550" height="400">


<img src="https://promanconsulting.hu/wp-content/uploads/2022/03/agilis-modszertanok-optimized.jpg" width="550" height="400">





## Reporting, Bugs
<img src="https://moolya.com/blog/wp-content/uploads/2023/05/Bug-Report.png" alt="image" width="300" height="220">

#### ✅ Milyen lépéseket követnél egy hiba megtalálásakor?
    Egy hiba (bug) megtalálásakor strukturált megközelítést érdemes követni, hogy a hiba pontosan dokumentálható, reprodukálható és javítható legyen. Az alábbi lépések egy tipikus hibakezelési folyamatot írnak le:
    1. A hiba azonosítása
    2. A hiba reprodukálása
    3. A hiba dokumentálása/bug report készítése
    4. A hiba továbbítása a fejlesztöőkhöz/ticket létrehozása
    5. Kommunikáció és követés
    6. Reteszt és regresszíós teszt
    7. A hiba lezárása

#### ✅ Beszélj a gyakori tesztjelentésekről és részleteikről!
    A gyakori tesztjelentések vagy tesztriportok általában a szoftvertesztelés, a minőségbiztosítás és a hibakeresés során készülnek, hogy dokumentálják a tesztelési folyamatot, az eredményeket és a hibákat. Ezeknek a jelentéseknek a célja a fejlesztők, tesztelők, projektmenedzserek és egyéb érintett személyek tájékoztatása az aktuális szoftverállapotról.
    Leggyakoribb tesztjelentések:

    - Tesztösszefoglaló jelentés (Test Summary Report)

    Ez egy magas szintű összefoglaló a tesztelési ciklusról, általában a projekt végén készül.

    Tartalma:
        - Projektazonosító, verziószám
        - Tesztelt funkciók
        - Tesztesetek száma, lefedettség
        - Átment / megbukott tesztek aránya
        - Talált hibák összesítése
        - Kockázatok és ajánlások


    - Hibajelentés (Bug Report / Defect Report)

    Egy adott hiba részletes leírása, amit a tesztelés során találtak.

    Tartalma:
        - Hibaazonosító (bug ID)
        - Rövid cím és részletes leírás
        - Lépések a hiba reprodukálásához
        - Elvárt vs. tényleges eredmény
        - Súlyosság (severity) és prioritás (priority)
        - Képernyőmentés, naplófájl vagy videó melléklet
        - Állapot (új, nyitott, javítva, lezárva stb.)


    - Teszteset-jelentés (Test Case Report)

    Egy konkrét teszteset végrehajtásának eredményeit dokumentálja.

    Tartalma:
        - Teszteset azonosító és leírás
        - Előfeltételek
        - Bemeneti adatok
        - Tesztlépések
        - Várt kimenet
        - Eredmény (sikeres / sikertelen)
        - Megjegyzések, hibák


    - Tesztfutási jelentés (Test Execution Report)

    Egy adott tesztelési ciklus alatt lefuttatott összes teszt eredményének összefoglalása.

    Tartalma:
        - Tesztelés dátuma és ideje
        - Futtatott tesztesetek száma
        - Sikeres / megbukott / kihagyott tesztek aránya
        - Tesztelési környezet (pl. operációs rendszer, böngésző)
        - Automatikus / manuális tesztelés megkülönböztetése


    - Automatizált teszt riportok

    Tesztkeretrendszerek (pl. JUnit, TestNG, Selenium, Allure, Jenkins stb.) által generált automatikus jelentések.

    Tartalmuk:
        - Diagramokat és statisztikákat
        - Futtatási időket
        - Tesztesetenkénti eredményeket
        - Linkeket a logokhoz vagy screenshotokhoz

#### ✅ Mit tartalmaz egy hibajelentés?
    A hibajelentés több "egységet" is tartalmaz. Minden egységnek van külön tartalma. Egy hibajelentés általános egységsorrendje a következő:
    - Cím
    - Hiba rövid leírása
    - A hiba reprodukciójának lépései
    - Az elvárt eredmény
    - Az adott eredmény
    - Más megjegyzések
    - Súlyosság
    - Környezet
    - Időpont
    - képernyőkép vagy videó a hibáról
    - Más csatolt fájlok
    - Logok
    - A tesztelő személye / "Aláírás"

    A cím egységben adunk egy problémához illő címet, amely röviden megadja a problémának a nevét, esetlegesen az adott eredményt is.
    A leírás szintén hasonló mint a cím, de terjedelmesebben leírva, magyarázva a hiba és problémái
    A hiba reprodukciójának lépéseiben megadjuk azt a folyamatot, amely megidézi a hibát, egészen a kezdetektől, például a bönjgésző megnyitásától.
    Az elvárt eredményben megadjuk 1-2 mondatban azt az eredményt, aminek történnie kéne egy hibátlan tesztben.
    Az adott eredmény az elvártnak ellentettje, ahol leírjuk hogy mi történt pontosan a tesztben.
    A csatolt fájlok egységben, legyen ez adott videó vagy más fájl, általában egy kép vagy videó szerepel amely láthatóan megmutatja a hibát, annak lépéseit.
    A tesztelő személyébe feltüntetjük a tesztelő nevét vagy aláírását (Ha a hibajelentés esetleg ki lett nyomtatva).
    Ezek egységeken kívül a többi az mind nem kötelező, de ajánlott belerakni.

#### ✅ Hogyan rangsorolnál egy hibát?
    A hibák rangsorolása súlyosság (severity) és prioritás (priority) alapján történik. Ez a rangsorolás segít eldönteni, mely hibákat kell előbb javítani, és milyen hatással van a hiba a rendszer működésére vagy az üzletre.

    1. Súlyosság:
        - Critical / Blocker
        - High / Major
        - Medium
        - Low / Minor
        - Trivial / Enhancement

    2. Prioritás:
        - P1 – Legmagasabb
        - P2 – Magas
        - P3 – Közepes
        - P4 – Alacsony


## Test Automation, Selenium
<img src="https://media.licdn.com/dms/image/C4D12AQE3GOyVsZazOw/article-cover_image-shrink_600_2000/0/1583830696602?e=2147483647&v=beta&t=bYHbKyhMoWsMgtEug6eSf3m0db5ZtGEl437TeS1qkfI" alt="image" width="320" height="220">

#### ✅ Melyik teszteseteket érdemes automatizálni és melyiket nem?
    Automatizálni jobban érdemes a funkciókat, elemeket, mivel ezek egy inputot követelnek. A legtöbb funkció automatizálható, és érdemes is automatizálni. Legtöbb esetben az egyedüli funkció amit nem ajánlott automatizálni az a regisztráció és bejelentkezés folyamata, hiszen sok adatbázisban van "bot-detection", amely robotként észleli az automatizált teszteket is.

#### ✅ Írj le egy jó automatizált tesztet!
    Egy jó automatizált teszt jól strukturált, stabil, könnyen karbantartható, és egyértelműen ellenőrzi, hogy egy funkció az elvártak szerint működik-e. Ez a teszt a hibás adatbevitel esetét vizsgálja, hogy megbizonyosodjunk arról, hogy a rendszer megfelelően jelez hibát, ha egy kötelező mező üresen marad.
``` python
import pytest
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys

@pytest.fixture
def driver():
    # Böngésző inicializálása
    driver = webdriver.Chrome()
    driver.implicitly_wait(10)
    yield driver
    driver.quit()

def test_registration_missing_fields(driver):
    # 1. Lépés: Nyisd meg a regisztrációs oldalt
    driver.get("https://example.com/register")

    # 2. Lépés: Ne töltsd ki a kötelező mezőket
    driver.find_element(By.ID, "username").send_keys("")  # Üres felhasználónév
    driver.find_element(By.ID, "password").send_keys("")  # Üres jelszó
    driver.find_element(By.ID, "email").send_keys("")     # Üres email

    # 3. Lépés: Kattints a 'Regisztráció' gombra
    driver.find_element(By.ID, "register-button").click()

    # 4. Lépés: Ellenőrizd, hogy a hibajelzés megjelenik
    error_message = driver.find_element(By.ID, "error-message").text
    assert "Minden mezőt ki kell tölteni" in error_message
```

#### ✅ Mi a Selenium, Selenium IDE és Selenium WebDriver?
    A Selenium az egyik legismertebb weboldalakra használt automatizált tesztelésre szolgáló keretrendszer. Ezzel a keretrendszerrel lehetséges egy webalkalmazásra való hatások, abban található hibák felvétele, illetve azok folyamatos ellenőrzése. A Selenium csak HTML és JavaScripten alapul.

    A Selenium IDE az a Seleniumnak az integrált fejlesztői környezete, amellyel lehetőve tehető a gyors tesztelés. Ezzel a környezettel felvehetőek, illetve újra lejátszhatóak a felhasználó (tesztelő) inputjai.

    A Selenium WebDriver natív módon hajtja meg a böngészőt, ahogy a felhasználó tenné, akár helyileg, akár egy távoli gépen a Selenium szerver segítségével.

#### ✅ Hogyan lehet azonosítani a webes elemeket?
    Seleniumban általában az elemek azonosítása XPath-tel működik. Az XPath egy adott oldalon lévő elemnek a pontos neve. Például ha egy oldalon a második bekezdést szeretnéd azonosítani, akkor az XPath az "/html/body/p[2]" lesz.

#### ✅ Hogyan lehet várni az elemekre, és mi lehet a probléma? Gyűjtsd össze a lehetséges hibákat és okokat!
    A várakozások kezelése az automatizált tesztelésben kulcsfontosságú, hogy megelőzzük a flaky teszteket, amelyek időnként hibásan futnak a dinamikus weboldalak vagy alkalmazások változó sebessége miatt. Ha nem kezeljük jól a várakozásokat, előfordulhat, hogy a teszt megpróbál elérni egy olyan elemet, amely még nem töltődött be, ami hibát eredményezhet.

    Típusai:
    1. Implicit várakozás (implicitly_wait)
    2. Explicit várakozás (WebDriverWait)
    
    - A várakozások hibás kezelése és lehetséges problémák
    
    1. Flaky tesztek:

    Probléma: A teszt nem következetesen fut le (egyes tesztfutások sikeresek, mások hibásak).

    Ok: Ha túl rövid időre vársz az elemekre, előfordulhat, hogy a rendszer nem töltötte még be teljesen az oldalt vagy az elemet, mire a teszt keresni próbálja. Ez hibákat eredményezhet.

    2. NoSuchElementException:

    Probléma: A Selenium nem találja meg az elemet, és NoSuchElementException hibát dob.

    Ok: Ez akkor történhet, ha az elem még nem töltődött be a DOM-ba (pl. az oldal dinamikusan töltődik), de a teszt már próbálja elérni.

    3. ElementNotInteractableException:

    Probléma: Az elem elérhető, de nem lehet vele interakcióba lépni (pl. nem kattintható, mert még nincs látható állapotban).

    Ok: A teszt nem várt elég időt az elemnek, hogy interaktívvá váljon (pl. egy gomb még nem enged kattintást).
     
    4. TimeoutException:

    Probléma: A teszt várakozása meghaladja a megadott időt, és nem találja meg az elemet.

    Ok: A keresett elem nem töltődött be időben (pl. lassú hálózati kapcsolat, szerver válaszidő problémák).

    5. StaleElementReferenceException:

    Probléma: A teszt azt az elemet próbálja használni, amely már eltűnt a DOM-ból, mivel a weboldal dinamikusan frissíti azt.

    Ok: Az elem egy olyan állapotban van, amikor a DOM frissítése után már nem érvényes. Például, amikor a teszt újratölti az oldalt vagy egy AJAX kérés frissíti az oldalt.

    6. Elemek nem jelennek meg a megfelelő sorrendben:

    Probléma: A teszt az elemekre nem a megfelelő sorrendben próbál várni, így ha egy elem nem a várt sorrendben töltődik be, akkor a teszt hibás eredményeket adhat.

    Ok: A DOM frissülése dinamikusan történhet, és nem garantált, hogy minden elem ugyanabban az időben vagy sorrendben lesz elérhető.

#### ✅ Hasonlítsd össze a POM és a Keyword Driven Testing megközelítéseket!
    A POM egy tervezési minta, amely segít a webautomatizálási kód rendszerezésében és karbantartásában azzal, hogy elválasztja a felhasználói felület elemeit a tesztlogikától. Minden weboldalt vagy összetevőt egy osztály képvisel, amely tartalmazza a lokátorokat és az adott oldalon lévő elemekkel való interakciós módszereket, így újra felhasználhatja ugyanazt a kódot különböző tesztesetekben, és a kódot olvashatóbbá, karbantarthatóbbá és méretezhetőbbé teheti.

    A Keyword Driven Testing egy olyan technika, amely lehetővé teszi a tesztesetek megírását olyan kulcsszavak vagy parancsok használatával, amelyek leírják a tesztelt alkalmazáson végrehajtandó műveleteket és ellenőrzéseket. A kulcsszavakat általában külső fájlokban, például Excel-táblázatokban vagy CSV-fájlokban tárolják, és egy illesztőprogram-szkript hajthatja végre, amely értelmezi őket, és meghívja a megfelelő függvényeket, így kódírás nélkül készíthet teszteseteket, és modulárisabbá és adatközpontúbbá teheti tesztjeit.

#### ✅ Mi a különbség a TDD és BDD között?
    A TDD az egységtesztekre, míg a BDD az elfogadási tesztelésre és a végpontok közötti forgatókönyvekre helyezi a hangsúlyt.

#### ✅ Mi az API tesztelés és miért hasznos?    
    Az API-tesztelés a szoftvertesztelés egy olyan formája, amely elemzi az API-t, és biztosítja, hogy az az elvárásoknak megfelelően, megbízhatóan, a teljesítményre gyakorolt káros hatás nélkül teljesíti funkcióit.

#### ✅ Mi az adatvezérelt tesztelés és miért hasznos?
    Az adatvezérelt tesztelés egy szoftvertesztelési módszer, amelyben a tesztadatokat táblázatban vagy táblázat formájában tárolják. Lehetővé teszi a tesztelők számára, hogy egyetlen tesztszkriptet vigyenek be, amely képes tesztelni egy tábla összes tesztadatát, és a tesztkimenetet ugyanabban a táblában várja. Táblázatvezérelt tesztelésnek vagy paraméterezett tesztelésnek is nevezik.