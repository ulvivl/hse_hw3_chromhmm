# hse_hw3_chromhmm

## Формулировка задания
 
[Условие](https://docs.google.com/document/d/1Kq3_L6URKQy5O2hg6qmfKQVgOm7fayuZ-BZsdQ7LCA4/edit)

---

## Colab

[Colab с кодом](https://colab.research.google.com/drive/1WAklSQC1NjeoRP9laFZL0vE7Yqka5hMp?usp=sharing)

---

## Информация о данных 

Клеточная линия | Гистоновая метка | Файл с гистоновой меткой | Имя при обработке 
--- | --- | --- | ---
A549 | H3K4me2 | wgEncodeBroadHistoneA549H3k04me2Dex100nmAlnRep1.bam | H3K04me2.bam
A549 | H3K79me2 | wgEncodeBroadHistoneA549H3k79me2Dex100nmAlnRep1.bam | H3K79me2.bam
A549 | H3K36me3 | wgEncodeBroadHistoneA549H3k36me3Dex100nmAlnRep1.bam | H3K36me3.bam
A549 | H4K20me1 |  wgEncodeBroadHistoneA549H4k20me1Etoh02AlnRep1.bam | H4K20me1.bam
A549 | H3K9me | wgEncodeBroadHistoneA549H3k09me3Etoh02AlnRep1.bam | H3K09me3.bam
A549 | H3K4me1 | wgEncodeBroadHistoneA549H3k04me1Dex100nmAlnRep1.bam | H3K04me1.bam
A549 | H3K27ac | wgEncodeBroadHistoneA549H3k27acDex100nmAlnRep1.bam | H3K27ac.bam
A549 | H3K9ac | wgEncodeBroadHistoneA549H3k09acEtoh02AlnRep1.bam | H3K09ac.bam
A549 | H3K4me3 | wgEncodeBroadHistoneA549H3k04me3Dex100nmAlnRep1.bam | H3K04me3.bam
A549 | H3K27me3 | wgEncodeBroadHistoneA549H3k27me3Dex100nmAlnRep1.bam | H3K27me3.bam

Файл с контрольным экспериментом | Имя при обработке
--- | --- 
wgEncodeBroadHistoneA549ControlDex100nmAlnRep1.bam | Control.bam

---

## ChromHMM

Emission | Overlap | Transition 
 --- | --- | ---
 ![](/img/emissions_10.png) | ![](/img/A549_10_overlap.png) | ![](/img/transitions_10.png)

RefSeqTSS | RefSeqTES 
 --- | --- 
![](/img/A549_10_RefSeqTSS_neighborhood.png) | ![](/img/A549_10_RefSeqTES_neighborhood.png)

---

## Эпигенетические состояния

1. Состояние 1:
   - Cостояние ярко выражено среди 2 гистоновых модификаций: H3K9me3 (только в ucsc), H3K27me3. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на ядерной ламине, то есть попадает на участок репрессированного гетерохроматима.
   - Не попадает на ген.
   - Больше всего похоже на состояние Heterochromatin
  
    ![](/img/state_1.png)
    
2. Состояние 2:
   - Cостояние встречается среди 4 гистоновых модификаций: H3K4me1 (только в ucsc), H3K9me3 (только в ucsc), H3K27me3 (только в ucsc), H3K20me1. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на ядерной ламине, то есть попадает на участок репрессированного гетерохроматима.
   - Не попадает на ген.
   - Больше всего похоже на состояние Repressed
  
    ![](/img/state_2.png)

3. Состояние 3:
   - Cостояние встречается среди 2 гистоновых модификаций: H3K9me3, H3K27me3 (только в ucsc). В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на ядерной ламине, то есть попадает на участок репрессированного гетерохроматима, но также на RefSeqTSS (но реже).
   - Не попадает на ген или попадает на интрон.
   - Больше всего похоже на состояние Weak transcribed (_Weak_Txn)
  
    Рисунок 1 | Рисунок 2
    --- | --- 
    ![](/img/state_3_1.png) | ![](/img/state_3_2.png)
  
4. Состояние 4:
   - Cостояние встречается среди 2 гистоновых модификаций: H3K9me3 (только в ucsc), H3K36me3, H3K79me2, H4K20me1. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на RefSeqTES, а также на RefSeqGene и RefSeqExon, но уже реже.
   - Попадает на интроны или на экзоны.
   - Больше всего похоже а состояние Weak transcribed (_Weak_Txn)
  
    ![](/img/state_4.png)
 
5. Состояние 5:
   - Cостояние встречается среди 4 гистоновых модификаций: H3K4me1, H3K79me2, H4K20me1, H3K36me3. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на RefSeqGene, а также на RefSeqTES и RefSeqExon, но реже.
   - Попадает на экзон или интрон.
   - Больше всего похоже на состояние Weak transcribed (_Weak_Txn)
  
    ![](/img/state_5.png)
   
6. Состояние 6:
   - Cостояние встречается среди 5 гистоновых модификаций: H3K4me1, H3K4me2, H3K4me3, H3K79me2, H4K20me1. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на RefSeqGene, а также RefSeqTES и RefSeqExon, но реже.
   - Попадает на интрон.
   - Больше всего похоже на состояние Weak enhancer (_Weak_Enhancer) или Weak transcribed (_Weak_Txn)
  
    ![](/img/state_6.png)
 
7. Состояние 7:
   - Cостояние встречается среди 4 гистоновых модификаций: H3K27ac, H3K4me1, H3K4me2, H3K9me3 (только в ucsc). В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на RefSeqTES, а также на ядерной ламине, но реже.
   - Попадает на интрон или не попадает ген.
   - Больше всего похоже на состояние Weak enhancer (_Weak_Enhancer) или Weak transcribed (_Weak_Txn)
  
    ![](/img/state_7.png) 
    
8. Состояние 8:
   - Cостояние встречается среди 5 гистоновых модификаций: H3K27ac, H3K4me1, H3K4me2, H3K9me3, H3K9ac. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на RefSeqTES и RefSeqTSS2Kb, а также на ядерной ламине, RefSeqGene и RefSeqExon, но реже.
   - Попадает на интрон.
   - Больше всего похоже на состояние Strong enhancer (_Strong_Enhancer) или Transcriptional elogation (_Txn_elogation)
  
    ![](/img/state_8.png) 
 
9. Состояние 9:
   - Cостояние встречается среди 5 гистоновых модификаций: H3K27ac, H3K4me1, H3K4me2, H3K9me3, H3K9ac. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на CpGIslands, RefSeqTES, RefSeqExon и RefSeqTSS2Kb, а также на RefSeqTES, но в реже.
   - Попадает на интрон или экзон или не попадает ген.
   - Больше всего похоже на состояние Active Promoter (_Active_Promoter)
  
    ![](/img/state_9.png) 
   
10. Состояние 10:
   - Cостояние встречается среди 7 гистоновых модификаций: H3K27ac, H3K4me1, H3K4me2, H3K9me3, H3K9ac, H3K79me2, H4K20me1. В других модификациях состояние либо не встречается либо едва заметно.
   - Чаще всего находятся на RefSeqTES и RefSeqTSS2Kb, а также на RefSeqExon, CpGIslands, и RefSeqGene, но реже.
   - Попадает на интрон или экзон или не попадает ген.
   - Больше всего похоже на состояние Active Promoter (_Active_Promoter)
  
   ![](/img/state_10.png)   
   
---

## Запущенные команды:

```
!wget link -O filename - для скачивания файлов
!touch filename - для создания файла
```
Для конвертации профилей из ChIP-seq экспериментов в бинарную табличку:
```
!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar BinarizeBam -b 200 \
  /content/ChromHMM/CHROMSIZES/hg19.txt /content/ cellmarkfiletable.txt binarizedData
```
Для определения 10 разных эпигенетических типов с наиболее выраженными наборами гистоновых меток и для присвоения каждому геномному интервалу определенный эпигенетический тип:
```
!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel -b 200 \
  /content/binarizedData/ /content/data 10 hg19
```

---

## Бонусная часть
Код представлен в колабе

![](/img/bonus.png)
