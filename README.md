# LeNER-Br with per-entity evaluation
[LeNER-Br: a Dataset for Named Entity Recognition in Brazilian Legal Text](https://cic.unb.br/~teodecampos/LeNER-Br/) 
  is a project developed as a collaboration between two institutions of the [University of Brasília](http://unb.br/):
    [NEXT (Núcleo de P&D para Excelência e Transformação do Setor Público)](http://next.unb.br/)
    and [CiC (Departamento de Ciência da Computação)](http://www.cic.unb.br/).

**I didn't have any participation in the original project.**

This repository was forked from the original code to add per-entity evaluation
  by means of the great [seqeval](https://github.com/chakki-works/seqeval) lib.
The original code included only per-token evaluation which is unusual for NER.
More information can be found in the [original work page](https://cic.unb.br/~teodecampos/LeNER-Br/).

In the following,
  one can see comparisons between per-token and per-entity evaluations over both dev and test sets.
Per-token results presented below vary a bit from the ones in the original paper since we have trained a new model.
Although we used the provided code, results may vary for different reasons.
Anyway,
per-entity results are a few points below the per-token results,
  as expected.
For the DEV set, overall per-entity f-score is around 7 points below per-token performance.
For the TEST set, the difference is around 6 points of f-score.

## Results on DEV set

**Per-token evaluation (original results)**
```
                precision    recall  f1-score   support

JURISPRUDENCIA     0.9165    0.7833    0.8447       743
         LOCAL     0.8614    0.5861    0.6976       244
         TEMPO     0.9550    0.9374    0.9461       543
        PESSOA     0.9808    0.9720    0.9764       894
    LEGISLACAO     0.9626    0.9360    0.9491      2609
   ORGANIZACAO     0.8944    0.8794    0.8868      1608

   avg / total     0.9390    0.8973    0.9165      6641

0.9182525618306496
```

**Per-entity evaluation**
```
Number of sentences: 1176
Number of tokens: 41166
                precision    recall  f1-score   support

         TEMPO     0.9198    0.9316    0.9257       234
   ORGANIZACAO     0.8309    0.8279    0.8294       552
    LEGISLACAO     0.8857    0.8589    0.8721       397
         LOCAL     0.7831    0.5963    0.6771       109
JURISPRUDENCIA     0.7469    0.5902    0.6594       205
        PESSOA     0.9435    0.9161    0.9296       310

     micro avg     0.8650    0.8224    0.8431      1807
     macro avg     0.8614    0.8224    0.8400      1807
```

## Results on TEST set

**Per-token evaluation (original results)**
```
                precision    recall  f1-score   support

JURISPRUDENCIA     0.9288    0.8697    0.8983       660
         LOCAL     0.7636    0.6364    0.6942       132
         TEMPO     0.8889    0.9231    0.9057       260
        PESSOA     0.9472    0.9034    0.9248       735
    LEGISLACAO     0.9697    0.9697    0.9697      2669
   ORGANIZACAO     0.9357    0.8413    0.8860      1367

   avg / total     0.9459    0.9102    0.9272      5823

0.9281961471103328
```

**Per-entity evaluation**
```
Number of sentences: 1389
Number of tokens: 47630
                precision    recall  f1-score   support

JURISPRUDENCIA     0.8280    0.8324    0.8302       185
   ORGANIZACAO     0.8804    0.8084    0.8429       501
         LOCAL     0.8000    0.6809    0.7356        47
        PESSOA     0.8510    0.7597    0.8027       233
    LEGISLACAO     0.9418    0.9418    0.9418       378
         TEMPO     0.8838    0.9115    0.8974       192

     micro avg     0.8837    0.8457    0.8643      1536
     macro avg     0.8827    0.8457    0.8631      1536
```
