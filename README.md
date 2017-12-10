# Praca_semestralna

Na liście argumentów możemy mieszać ze sobą zmienne różnych typów, liczby, napisy itp. w dowolnej liczbie. Funkcja printf przyjmie ich tyle, ile tylko napiszemy. Należy uważać, by nie pomylić się w formatowaniu:

  int i = 5;
  printf("%i %s %i", 5, 4, "napis"); /* powinno być: "%i %i %s" */

Przy włączeniu ostrzeżeń (opcja -Wall lub -Wformat w GCC) kompilator powinien nas ostrzec, gdy format nie odpowiada podanym elementom.
