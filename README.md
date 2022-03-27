# hse_hw3_chromhmm

## [colab](https://colab.research.google.com/drive/1o8tPpzsJhZQGDrfLjEE-No_bWGXLHSbN?usp=sharing)

## Table with files for A549
| Гистоновая метка        | Файл           | Имя  |
| ------------- |:-------------:| -----:|
| H2AFZ    | wgEncodeBroadHistoneA549H2azDex100nmAlnRep1.bam          | H2azDex100.bam  |
| H3K27ac  | wgEncodeBroadHistoneA549H3k27acDex100nmAlnRep1.bam       |   H3k27ac.bam   | 
| H3K27me3 | wgEncodeBroadHistoneA549H3k27me3Dex100nmAlnRep1.bam      |    H3K27me3.bam |
| H3K36me3 | wgEncodeBroadHistoneA549H3k36me3Dex100nmAlnRep1.bam      |    H3K36me3.bam |
| H3K4me1  | wgEncodeBroadHistoneA549H3k04me1Dex100nmAlnRep1.bam	    |    H3K04me1.bam |
| H3K4me2  | wgEncodeBroadHistoneA549H3k04me2Dex100nmAlnRep1.bam	    |    H3K04me2.bam |
| H3K4me3  | wgEncodeBroadHistoneA549H3k04me3Dex100nmAlnRep1.bam      |    H3K04me3.bam |
| H3K79me2 | wgEncodeBroadHistoneA549H3k79me2Dex100nmAlnRep1.bam      |    H3K79me2.bam |
| H3K9ac   | wgEncodeBroadHistoneA549H3k09acEtoh02AlnRep1.bam         |    H3K09ac.bam  |
| H3K9me3  | wgEncodeBroadHistoneA549H3k09me3Etoh02AlnRep1.bam        |   H3K09me3.bam  |

## ChromHMM
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2015.28.23.png)
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2015.28.28.png)
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2015.28.33.png)
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2015.28.36.png)
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2015.28.40.png)

## Эпигенетические типы
*1 - Состояние попадает на H3K27me3 и H3K9me3*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.45.40.png)

*2 - Состояние попадает на H3K27me3, H3K20me1 и H3K4me1*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.46.04.png)

*3 - Состояние попадает на H3K27me3 и H3K9me3*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.46.20.png)

*4-5 - Состояния попадают на H3K9me3, H3K79me2, H3K36me3*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.46.35.png)

*6 - Состояние попадает на H3K4me2, H3K4me1 и H3K79me2*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.46.58.png)

*7 - Состояние попадает на H3K27ac и H3K9me3*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.47.15.png)

*8 - Состояние попадает на H3K4me3, H3K4me2, H3K4me2 и H3K27ac*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.47.34.png)

*9 - Состояние попадает на H3K27ac, H3K9ac, H3K4me1, H3K4me2, H3K4me3*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.48.04.png)

*10 - Состояние попадает на H3K27ac, H3K4me1, H3K4me2, H3K9me3, H3K9ac, H3K79me2*
![alt text](https://github.com/messlav/hse_hw3_chromhmm2/blob/main/images/Снимок%20экрана%202022-03-27%20в%2016.48.26.png)

## Список всех запущенных команд
```
! wget [link_to_file] -O file_name  # download file
! touch file_name  # create empty file
! java -mx5000M -jar /content/ChromHMM/ChromHMM.jar BinarizeBam -b 200  /content/ChromHMM/CHROMSIZES/hg19.txt /content/ cellmarkfiletable.txt   binarizedData  # convert profiles from CHIP-seq experiments into table 
! java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel -b 200 /content/binarizedData/ /content/data 10 hg19  # определение параметров 10 разных эпигенетических типов с наиболее выраженными наборами гистоновых меток и присвоение каждому геномному интервалу определенный эпигенетический тип
```
