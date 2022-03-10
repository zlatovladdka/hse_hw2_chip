# hse_hw2_chip

https://colab.research.google.com/drive/1CRy1_utxf2XMosLucnf2WeM0QdEgwj_U#scrollTo=q9scmDGtGUDu

## Анализ fastqc

| XKC | CNX |
| :-: | :-: |
| ![](img/xkc_bs.png) | ![](img/cnx_bs.png) | 
| ![](img/xkc_pbsq.png) | ![](img/cnx_pbsq.png) |
| ![](img/xkc_pbsc.png) | ![](img/cnx_pbsc.png) |
| ![](img/xkc_psgc.png) | ![](img/cnx_psgc.png) |

Все чтения почти полностью лежат в зелёной области, только ближе к концу кресты погрешностей начинают вылезать вниз в желтую область. Нужды подрезать или фильтровать чтения нет. Ради интереса попробуем подрезать чтения контрольного образца и сравним результат.

| KUS | KUS trimmed |
| :-: | :-: |
| ![](img/kus_bs.png) | ![](img/kust_bs.png) | 
| ![](img/kus_pbsq.png) | ![](img/kust_pbsq.png) |
| ![](img/kus_ptsq.png) | ![](img/kust_ptsq.png) |
| ![](img/kus_pbsc.png) | ![](img/kust_pbsc.png) |
| ![](img/kus_psgc.png) | ![](img/kust_psgc.png) |

Как видно из таблицы, общее качество чтений стало совсем немного лучше, при этом в остальном улучшений не было. Более того, в самих html-отчетах можно увидеть, что распределение длин последовательность в подрезанных чтениях стало "пограничным" по качеству. Несмотря на это, в дальнейшем будем работать с подрезанным контрольным образцом, гонясь за небольшим выигрышом в общем качестве чтений.

## Выравнивание

| Образец | Всего ридов | Уникально | Не уникально | Не выровнилось |
| :----- | :-: | :-: | :-: | :-: |
| XKC | 30415753  | 1102854 (3.63%)  | 1715569 (5.64%) | 27597330 (90.73%) |
| CNX | 30415753 | 1091512 (3.59%) | 1734863 (5.70%) | 27589378 (90.71%) |
| KUS | 34133287 | 1091512 (3.59%) |  1734863 (5.70%) | 27589378 (90.71%) |

Общий процент выравниваний довольно низкий из-за того, что выравнивали всего на одну хромосому, а не на полный геном.

## Диграммы Венна

Забыл указать названия, поэтому на картинках будет просто N/A, прошу прощения...

### XKC

![](img/v1.png)
![](img/v2.png)

### CNX

![](img/v3.png)
![](img/v4.png)

Скорее всего, пересений довольно мало ввиду того, что выравнивание проводилось на одну хромосому. Различие в пересечениях можеть быть вызвано неуникальностью позиций пиков.

## Бонус

Досчитаться не успел, но в колабе есть ячейки, которые были запущены...
