# waves over lambda

## Objetivo

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with nc jupiter.challenges.picoctf.org 39894.

## Solución

```bash
hone@unidad03:~/waves_over_lambda$ nc jupiter.challenges.picoctf.org 39894
-------------------------------------------------------------------------------
juactres xdtd fs bult hnrc - htdvldajb_fs_j_uqdt_nrmzyr_rchnjcebld
-------------------------------------------------------------------------------
kd kdtd aue mljx mutd exra r vlrtedt uh ra xult ule uh ult sxfw efnn kd srk xdt sfap, ray exda f laydtseuuy hut exd hftse efmd kxre krs mdrae zb r sxfw hulaydtfac fa exd sdr.  f mlse rjpaukndycd f xry xrtynb dbds eu nuup lw kxda exd sdrmda euny md sxd krs sfapfac; hut htum exd mumdae exre exdb trexdt wle md faeu exd zure exra exre f mfcxe zd srfy eu cu fa, mb xdrte krs, rs fe kdtd, ydry kfexfa md, wrtenb kfex htfcxe, wrtenb kfex xuttut uh mfay, ray exd exulcxes uh kxre krs bde zdhutd md.
```

Se desencripta el desencripta el texto utilizando un *Substitution cipher decoder* para obtener lo siguente

```
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_agflcgtyue
-------------------------------------------------------------------------------
we were not much more than a quarter of an hour out of our ship till we saw her sink, and then i understood for the first time what was meant by a ship foundering in the sea.  i must acknowledge i had hardly eyes to look up when the seamen told me she was sinking; for from the moment that they rather put me into the boat than that i might be said to go in, my heart was, as it were, dead within me, partly with fright, partly with horror of mind, and the thoughts of what was yet before me.
```

Bandera: *frequency_is_c_over_lambda_agflcgtyue*

## Referencias

[Substitution cipher decoder](https://planetcalc.com/8047/)
