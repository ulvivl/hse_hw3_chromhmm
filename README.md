# hse_hw3_chromhmm

## Colab
[ссылка]()

## Гистоновые Метки
Name | File
--- | ---
H3K4me2 | wgEncodeBroadHistoneA549H3k04me2Dex100nmAlnRep1.bam
H3K79me2 | wgEncodeBroadHistoneA549H3k79me2Dex100nmAlnRep1.bam
H3K36me3 | wgEncodeBroadHistoneA549H3k36me3Dex100nmAlnRep1.bam
H4K20me1 | wgEncodeBroadHistoneA549H4k20me1Etoh02AlnRep1.bam
H3K9me3 | wgEncodeBroadHistoneA549H3k09me3Etoh02AlnRep1.bam
H3K4me1 | wgEncodeBroadHistoneA549H3k04me1Dex100nmAlnRep1.bam
H3K27ac | wgEncodeBroadHistoneA549H3k27acDex100nmAlnRep1.bam
H3K9ac | wgEncodeBroadHistoneA549H3k09acEtoh02AlnRep1.bam
H3K4me3 | wgEncodeBroadHistoneA549H3k04me3Dex100nmAlnRep1.bam
H3K27me3 | wgEncodeBroadHistoneA549H3k27me3Dex100nmAlnRep1.bam


## cellmarkfiletable.txt

Клеточная линия | Гистоновая метка | Файл с гистоновой меткой | Файл с контролем
--- | --- | --- | ---
A549 | H3K4me2 | H3K4me2.bam | Control.bam
A549 | H3K79me2 | H3K79me2.bam | Control.bam
A549 | H3K36me3 | H3K36me3.bam | Control.bam
A549 | H4K20me1 | H4K20me1.bam | Control.bam
A549 | H3K9me | H3K9me.bam | Control.bam
A549 | H3K4me1 | H3K4me1.bam | Control.bam
A549 | H3K27ac | H3K27ac.bam | Control.bam
A549 | H3K9ac | H3K9ac.bam | Control.bam
A549 | H3K4me3 | H3K4me3.bam | Control.bam
A549 | H3K27me3 | H3K27me3.bam | Control.bam


## ChromHMM

Emission | Transition 
 --- | ---
 ![](/img/A549_10_overlap.png) | ![](/img/transitions_10.png)

RefSeqTSS | RefSeqTES 
 --- | --- 
![](/img/A549_10_RefSeqTSS_neighborhood.png) | ![](/img/A549_10_RefSeqTES_neighborhood.png)

## Эпигенетические типы


№ | Название | Описание | Картинка
| --- | --- | ---| ---
1 |Heterochromatin | Заметим, что состояние  не встречается среди выбранных нами гистоновых модификациях, кроме H3k09me3AlnRep1. </li><li>Чаще всего ассоциировано с ядерной ламиной, то есть попаает на участок репрессированного гетерохроматима.</li><li>Данное состояние попадает на интрон гена </li><li>Показывает низкий сигнал.</li><li>Из примерного списка состояний ближе всего к состоянию Heterochromatin</li></ul>| ![Image](/img/image_1.png)
 
