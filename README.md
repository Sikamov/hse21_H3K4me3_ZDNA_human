# Отчет по проекту 
Выполнил студент 3-го курса факультета физики: Сикамов Кирилл Витальевич


# Обзор результатов
## Гистограмма распределения длин ChIP-seq пиков до фильтрации
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/len_hist.H3K4me3_H1.ENCFF456NIF.hg38.png)
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/len_hist.H3K4me3_H1.ENCFF456NIF.hg19.png)
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/len_hist.H3K4me3_H1.ENCFF277AOQ.hg38.png)
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/len_hist.H3K4me3_H1.ENCFF277AOQ.hg19.png)

## Гистограмма распределения длин ChIP-seq пиков после фильтрации
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/filter_peaks.H3K4me3_H1.ENCFF456NIF.hg19.filtered.hist.png)
### Параметр фильтрации для ENCFF456NIF: 7500 
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/filter_peaks.H3K4me3_H1.ENCFF277AOQ.hg19.filtered.hist.png)
### Параметр фильтрации для ENCFF277AOQ: 5000

## Положение ChIP-seq пиков относительно аннотированных генов
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/chip_seeker.H3K4me3_H1.ENCFF277AOQ.hg19.filtered.plotAnnoPie.png)
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/chip_seeker.H3K4me3_H1.ENCFF456NIF.hg19.filtered.plotAnnoPie.png)

## Гистограмма распределения длин участков вторичной структуры ДНК 
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/len_hist.zhunt.png)

## Расположение вторичных структур ДНК относительно аннотированных генов
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/chip_seeker.zhunt.plotAnnoPie.png)

## Гистограмма длин пересечения пиков ChIP-seq и вторичных структур ДНК
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/len_hist.H3K4me3_H1.intersect_with_ZHunt.png)

## Расположение пересечения пиков ChIP-seq и вторичных структур ДНК относительно аннотированных генов
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/chip_seeker.H3K4me3_H1.intersect_with_ZHunt.plotAnnoPie.png)

## Визуализация в UCSC GenomeBrowser
### UCSC GenomeBrowser сессия:  
https://genome.ucsc.edu/s/SikamovK/hse21_H3K4me3_ZDNA_human
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/Genome_browser.png)

## Ассоциация пиков с генами 
### Количество пиков, которые могут быть связаны с генами: 7097
### Количество уникальных генов: 4721

## GO-анализ
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/GO_analysis.png)
