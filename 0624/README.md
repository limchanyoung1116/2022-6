Neptune, Roary, Scoary
======================   
<br/><br/>

## Roary, Scoary
<br/>

#### Roary input file
Streptococcus Thermophilus 6 genome///ST.non thermo 20 genome
<br/>
gff3 파일 끝에 \n##FASTA\n 치고 fna 파일 붙여넣기
<br/>
Roary *.gff
<br/>

#### Roary output file
gene presence/absence.csv 형식
+phenotype.csv 만들어서 Scoary 진행
<br/>

#### Scoary
scoary.py -g <gene_presence_absence.csv> -t <traits.csv>
<br/>
해당 phenotype이 있는 include genome들과 phenotype이 없는 exclude genome들에서,
<br/>
각각의 gene이 얼마나 등장하는지, max/min값은 어떤지 정보들을 csv로 return
<br/><br/>

## Neptune
<br/>

#### Streptococcus Thermophilus 6 genome///ST.non thermo 20 genome
N00002\~N00006,N00139(S.thermo representative)///N00000,N00001,N000162\~N000179
<br/>
k = 10, k = 13, k = 16, k = 19, k = 22, k = 25, k = 28로 k-mer를 잡고 fna와 cds_fna에 대해 각각 실행
<br/><br/>

#### 결과
fna k=10 : no signiture   
fna k=13 : no signiture   
fna k=16 : score>=0.9 96seq, whole 384seq   
fna k=19 : score>=0.9 144seq, whole 576seq
fna k=22 : score>=0.9 71seq, whole 276seq
fna k=25 : score>=0.9 56seq, whole 224seq
fna k=28 : score>=0.9 58seq, whole 203seq

cds k=10 : no signiture
cds k=13 : no signiture
cds k=16 : score>=0.9 88seq, whole 384seq
cds k=19 : score>=0.9 111seq, whole 496seq
cds k=22 : score>=0.9 69seq, whole 286seq
cds k=25 : score>=0.9 67seq, whole 256seq
cds k=28 : score>=0.9 64seq, whole 237seq
<br/><br/>

#### length, score 그래프 그리기
파이썬으로 각 seq contig에 대해 length, score 추출 후 csv 파일로 만들고 excel에서 그래프 만들기
나중에는 R로 할 예정. 지금은 R을 쓸줄 모르므로 엑셀로 진행
