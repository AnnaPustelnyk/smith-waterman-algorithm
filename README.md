# smith-waterman-algorithm
Program implementuje algorytm Smith-Waterman do lokalnego dopasowania dwóch sekwencji. Program pozwala użytkownikowi wprowadzić dwie sekwencje z pliku w formacie FASTA i zapisuje wynikowe dopasowanie do pliku wynikowego.

# Sposób użycia

Aby uruchomić program, należy użyć następującej składni:

  Jeżeli sekwencji znajdują się w rożnych plikach FASTA:
	
    python Script.py <ścieżka_do_pliku_fasta1> <ścieżka_do_pliku_fasta2>
		
  lub jezeli dwie sekwencji znajduje się w jednym pliku FASTA:
	
    python Scripy.py <plik_fasta>

Program wczytuje sekwencje z plików(lub pliku) FASTA i przeprowadza lokalne dopasowanie. 

# Wynik

Po uruchomieniu programu, wynikowe dopasowanie zostanie zapisane do pliku "aligned_sequences.txt" w bieżącym katalogu. Plik ten zawiera dopasowane sekwencje aminokwasowe.

# Uwagi

  W przypadku wielu alternatywnych dopasowań, program zapisuje jedno z nich.

  Program zakłada domyślne punktacje: 1 za dopasowanie, -1 za niezgodność i -2 za przerwę. Możesz dostosować te wartości w kodzie programu, zmieniając argumenty 	   funkcji smith_waterman().

# Przykład
Plik FASTA rcsb_pdb_142D.fa zawiera dwie sekwencje DNA, każda z nich jest opisana nagłówkiem rozpoczynającym się od znaku >. Oto zawartość pliku:
 
 	142D_1|Chain A|DNA (5'-D(*AP*GP*CP*TP*TP*GP*CP*CP*TP*TP*GP*AP*G)-3')|null
	AGCTTGCCTTGAG
	>142D_2|Chain B|DNA (5'-D(*CP*TP*CP*AP*AP*GP*GP*CP*AP*AP*GP*CP*T)-3')|null
	CTCAAGGCAAGCT
Dla uruchomienia danego pliku należy użyc polecenia:

	python3 Script.py rcsb_pdb_142D.fa
Skrypt odczytuje dwie sekwencje z pliku rcsb_pdb_142D.fa, a następnie wykonuje dopasowanie za pomocą algorytmu Smitha-Watermana. Wynik działania skryptu zostanie zapisany do pliku aligned_sequences.txt.

Po przeprowadzeniu algorytmu Smitha-Watermana dla dwóch sekwencji DNA, otrzymamy następujący wynik:
![Знімок екрана 2023-11-06 173745](https://github.com/AnnaPustelnyk/smith-waterman-algorithm/assets/127084117/f8961ea1-5c18-400f-bd08-186f20fc789d)

Czyli najlepszym dopasowaniem jest:
		
	AGCT
	****
	AGCT

 Takiego wyniku możemy spodziewać się od programu.
 
 W pliku wynikowym programu znajduje się następujące rozwiązanie:
 
	Aligned Sequence 1: AGCT
	Aligned Sequence 2: AGCT

 Czyli otrzymaliśmy taki sam wynik, jak i powinniśmy.

