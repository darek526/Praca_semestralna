# Praca_semestralna

Na liście argumentów możemy mieszać ze sobą zmienne różnych typów, liczby, napisy itp. w dowolnej liczbie. Funkcja printf przyjmie ich tyle, ile tylko napiszemy. Należy uważać, by nie pomylić się w formatowaniu:

  int i = 5;
  printf("%i %s %i", 5, 4, "napis"); /* powinno być: "%i %i %s" */

Przy włączeniu ostrzeżeń (opcja -Wall lub -Wformat w GCC) kompilator powinien nas ostrzec, gdy format nie odpowiada podanym elementom.


Rozpatrzmy teraz trochę bardziej skomplikowany przykład. Otóż, ponownie jak poprzednio nasz program będzie wypisywał trzecią potęgę podanej liczby, ale tym razem musi ignorować błędne dane (tzn. pomijać ciągi znaków, które nie są liczbami) i kończyć działanie tylko w momencie, gdy nastąpi błąd odczytu lub koniec pliku[3].

#include <stdio.h>
  int main(void)
 {
   int result, n;
   do 
   {
     result = scanf("%d", &n);
     if (result) /* result to to samo co result!=0 */
       printf("%d\n", n*n*n);
     else
       result = scanf("%*s");
   } 
   while (result!=EOF);
   return 0;
 }
 
Zastanówmy się przez chwilę co się dzieje w programie. Najpierw wywoływana jest funkcja scanf() i następuje próba odczytu liczby typu int. Jeżeli funkcja zwróciła 1 to liczba została poprawnie odczytana i następuje wypisanie jej trzeciej potęgi. Jeżeli funkcja zwróciła 0 to na wejściu były jakieś dane, które nie wyglądały jak liczba. W tej sytuacji wywołujemy funkcję scanf() z formatem odczytującym dowolny ciąg znaków nie będący białymi znakami z jednoczesnym określeniem, żeby nie zapisywała nigdzie wyniku. W ten sposób niepoprawnie wpisana dana jest omijana. Pętla główna wykonuje się tak długo jak długo funkcja scanf() nie zwróci wartości EOF.
