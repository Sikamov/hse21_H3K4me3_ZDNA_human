# Отчет по проекту 
Выполнил студент 3-го курса факультета физики: Сикамов Кирилл Витальевич

# Введение
Целью работы над проектом является поиск и изучение участков генома, где определенная гистоновая метка присутствует в местах образования одной из вторичных структур ДНК
Для исследования я выбрал гистоновую метку: H3K4me3, тип клетки: H1 и вторичную структуру ДНК: ZNDA (Zhunt)

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
### ENCFF277AOQ
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/chip_seeker.H3K4me3_H1.ENCFF277AOQ.hg19.filtered.plotAnnoPie.png)
### ENCFF456NIF
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
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/Genome_browser_1.png)

## Ассоциация пиков с генами 
### Количество пиков, которые могут быть связаны с генами: 7097
### Количество уникальных генов: 4721

## GO-анализ
![alt text](https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human/blob/main/images/GO_analysis.png)


# Используемые команды

### Скачивание и обрезание bed.файлов:

•	mkdir ~/project

•	wget https://www.encodeproject.org/files/ENCFF456NIF/@@download/ENCFF456NIF.bed.gz

•	wget https://www.encodeproject.org/files/ENCFF277AOQ/@@download/ENCFF277AOQ.bed.gz

•	zcat ENCFF277AOQ.bed.gz | cut -f1-5 > H3K4me3_H1.ENCFF277AOQ.hg38.bed

•	zcat ENCFF456NIF.bed.gz | cut -f1-5 > H3K4me3_H1. ENCFF456NIF.hg38.bed

### Конвертирование версии генома:

•	wget https://hgdownload.cse.ucsc.edu/goldenpath/hg38/liftOver/hg38ToHg19.over.chain.gz

•	liftOver   H3K4me3_H1.ENCFF277AOQ.hg38.bed   hg38ToHg19.over.chain.gz   H3K4me3_H1.ENCFF277AOQ.hg19.bed   H3K4me3_H1.ENCFF277AOQ.unmapped.bed

•	liftOver   H3K4me3_H1.ENCFF277AOQ.hg38.bed   hg38ToHg19.over.chain.gz   H3K4me3_H1.ENCFF277AOQ.hg19.bed   H3K4me3_H1. ENCFF456NIF.unmapped.bed

### Объединяем два набора отфильтрованных ChIP-seq:

•	cat  *.filtered.bed  |   sort -k1,1 -k2,2n   |   bedtools merge   >  H3K4me3_H1.merge.hg19.bed 

### GitHub <–> Сервер:

•	mkdir github

•	git clone https://github.com/Sikamov/hse21_H3K4me3_ZDNA_human

•	   git config --global user.email "sikamov.kirill@mail.ru"

•	git config --global user.name "Sikamov"

•	git add README.md data/

•	git commit -m 'Initial .bed files'

•	    git push     (/pull)

### Скачивание вторичной структуры ДНК (ZDNA):

•	wget https://raw.githubusercontent.com/Nazar1997/DeepZ/master/annotation/zhunt.bed

### Пересечения гистоновой метки и вторичной структуры ДНК:

•	bedtools intersect  -a zhunt.bed   -b  H3K4me3_H1.merge.hg19.bed  >  H3K4me3_H1.intersect_with_ZHunt.bed

### Визуализация в геномном браузере:

•	track visibility=dense name="ENCFF456NIF"  description="H3K4me3_H1.ENCFF456NIF.hg19.filtered.bed"
https://raw.githubusercontent.com/Sikamov/hse21_H3K4me3_ZDNA_human/main/data/H3K4me3_H1.ENCFF456NIF.hg19.filtered.bed

•	track visibility=dense name="ENCFF277AOQ"  description="H3K4me3_H1.ENCFF277AOQ.hg19.filtered.bed"
https://raw.githubusercontent.com/Sikamov/hse21_H3K4me3_ZDNA_human/main/data/H3K4me3_H1.ENCFF277AOQ.hg19.filtered.bed

•	track visibility=dense name="ChIP_merge"  color=50,50,200   description="H3K4me3_H1.merge.hg19.bed"
https://raw.githubusercontent.com/Sikamov/hse21_H3K4me3_ZDNA_human/main/data/H3K4me3_H1.merge.hg19.bedtrack 

•	visibility=dense name="ZHunt"  color=0,200,0  description="ZHunt"
https://raw.githubusercontent.com/Sikamov/hse21_H3K4me3_ZDNA_human/main/data/zhunt.bed

•	track visibility=dense name="intersect_with_ZHunt"  color=200,0,0  description="H3K4me3_A549.intersect_with_ZHunt.bed"
https://raw.githubusercontent.com/Sikamov/hse21_H3K4me3_ZDNA_human/main/data/H3K4me3_H1.intersect_with_ZHunt.bed

