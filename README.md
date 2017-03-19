# Herring

Projekt zaliczeniowy z przedmiotu "Zaawansowana eksploracja danych".

### Raport

http://martin.berent.student.put.poznan.pl/herring/

### Wymagania

http://www.cs.put.poznan.pl/dbrzezinski/teaching/zedZaoczne/zed_projekt_2016-2017_zaoczne.html

### Streszczenie

Przedmiotem poniższej analizy jest określenie dlaczego długość śledzia oceanicznego wyławianego w Europie w pewnym momencie zaczeła spadać. W ramach analizy dysponowano ponad 52 tysiącami obserwacji dokonanych podczas połowów. Dla każdej obserwacji odnotowane zostały dane dotyczące dostępności planktonu, warunków środowiskowych oraz eksploatacji łowisk. Rozmiar śledzia określany był na podstawie próbki o rozmiarze od 50 do 100 trzy letnich śledzi.

W ramach raportu przedstawiono podstawowe statystyki dla każdej cechy. Dokonano szczegółowej analizy rozkładu danych, co pomogło w określeniu i usunięciu wartości odstających. W następnym kroku przeprowadzono inspekcję wartości pustych. Zbadano ich udział, rozkład oraz strukturę. Na tej podstawie użyto filtru Kalmana do wypełnienia wartości pustych. Po wstępnym przetwarzaniu danych przeanalizowano korelację cech. Zauważono że wielkość sledzia jest wysoce skorelowana z temperaturą przy powierzchni wody. Dodatkowo zobrazowano zależność wpływu oscylacji północnoatlantyckiej na dostępność planktonu Calanus helgolandicus gat. 1 i Widłonogów gat. 1. Dysponując danymi uszeregowanymi chronologicznie w następnym kroku podjęto próbę zobrazowania zależności czasowych dla trzech grup cech: dostępności planktonu, warunków środowiskowych oraz ekploatacji łowisk. Przedstawiono również zmianę rozmiarów śledzia na przestrzeni kolejnych połowów.

W ostatnim etapie zbudowano dwa modele regresji przewidujące rozmiar śledzia. Modele te zostały poddane ocenie R-square i RMSE oraz porównane ze sobą. Dla każdego modelu określono ważność atrybutów. Wyniki te w dużym stopniu potwierdziły silną zalezność rozmiaru śledzia z temperatura przy powierzchni wody.
