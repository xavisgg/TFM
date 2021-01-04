# TFM

## Descripció
Aquest repositori conté els elements desenvolupats durant el projecte final de màster corresponent al màster en ciencia de dades de la Universitat Oberta de Catalunya.

El projecte es realitza dins de l'àrea de Deep Learning i Machine Learning, i dins d'aquest s'han desenvolupat dos models per a l'anàlisi visual del sentiments que determinen si una imatge evoca sentiments negatius, neutres o positius. Els models generats dins d'aquest treball han estat creats utilitzant com a models base les arquitectures ResNet50 i SEResNet50 respectivament.

## Fitxers entregats
### Memòria 
- **pdf/xavisgg_TFM.pdf:** Memòria del treball final.

### Jupyter Notebooks desenvolupats
- **src/TFM_models_train.ipynb:** Jupyter Notebook utilitzat per a l'entrenament dels models.
- **src/TFM_models_test.ipynb:** Jupyter Notebook que conté els tests realitzats sobre els models generats.

### Històric d'entrenaments

#### Model basat en arquitectura ResNet-50
- **resnet50_weights_adam.hdf5:** Pesos del model entrenat basat en l'arquitectura ResNet50 utilitzant l'optimitzador Adam.
- **data/resnet50_fit_hist_adam_part1.npy:** Històric de la primera part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Adam.
- **data/resnet50_fit_hist_adam_part2.npy:** Històric de la segona part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Adam.

- **resnet50_CP_weights_SGD_NAG.hdf5:** Pesos del model entrenat basat en l'arquitectura ResNet50 utilitzant l'optimitzador Adam.
- **data/resnet50_fit_hist_SGD_NAG_part1.npy:** Històric de la primera part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador SGD amb momentum      Nesterov.
- **data/resnet50_fit_hist_SGD_NAG_part1.npy:** Històric de la segona part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador SGD amb momentum          Nesterov.


- **resnet50_weights_nadam.hdf5:** Pesos del model entrenat basat en l'arquitectura ResNet50 utilitzant l'optimitzador Nadam.
- **data/resnet50_fit_hist_nadam_part1.npy:** Històric de la primera part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Nadam.
- **data/resnet50_fit_hist_nadam_part2.npy:** Històric de la segona part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Nadam.


#### Model basat en arquitectura SE-ResNet-50

- **seresnet50_weights_adam.hdf5:** Pesos del model entrenat utilitzant el optimitzador Nadam.
- **data/seresnet50_fit_hist_adam_part1.npy:** Històric de la primera part de l'entrenament del model utilitzant l'optimitzador Adam.
- **data/seresnet50_fit_hist_adam_part2.npy:** Històric de la segona part de l'entrenament del model  utilitzant l'optimitzador Adam.

- **data/seresnet50_CP_weights_SGD_NAG.hdf5:** Pesos del model entrenat basat en l'arquitectura ResNet50 utilitzant l'optimitzador Adam.
- **data/seresnet50_fit_hist_SGD_NAG_part1.npy:** Històric de la primera part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador SGD amb momentum      Nesterov.
- **data/seresnet50_fit_hist_SGD_NAG_part2.npy:** Històric de la segona part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador SGD amb momentum          Nesterov.


- **seresnet50_CP_weights_nadam.hdf5:** Pesos del model entrenat basat en l'arquitectura ResNet50 utilitzant l'optimitzador Nadam.
- **data/seresnet50_fit_hist_nadam_part1.npy:** Històric de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Nadam.

Els fitxers corresponents als pesos dels models generats així com els històrics d'entrenaments estan disponibles en aquest [enllaç](www.kaggle.com/dataset/e2add917e9b4b51fb8aa857aa92d7f65e38ab2fd073efdd3692fe5a44aec6cb6).

Les imatges utiltizades durant l'entrenament dels models poden ser obtingudes [aquí](www.kaggle.com/dataset/a0bb539e95b3d6cd2e948996deb674493e5955384d83c368d4f02a69d029db27) per al cas del conjunt generat a partir del dataset [B-T4SA](http://www.t4sa.it/) mentre que les imatges del segon conjunt de test, _Twitter Dataset_, poden ser descarregades desde la web dels creadors [aquí](https://www.ee.columbia.edu/ln/dvmm/vso/download/twitter_dataset.html).

## Configuració dels Jupyter Notebooks
### tfm-models-train
Aquest Notebook executa l'entrenament del model sel·leccionat. A més, donada la limitació de sessions continues a Kaggle de 9h com a màxim, el Notebook permet la inicialització dels pesos basat en el dataset _ImageNet_ o bé carregar els pesos d'una sessió anterior per tal de continuar l'entrenament del model. Els paràmetres a modificar en aquest Notebook per tal de triar el comportament desitjat son:

- **continue_training** 
  - False - Inicialitza els pesos de la xarxa amb els pesos del dataset del model pre-entrenat amb el conjunt _ImageNet_ per a la part corresponent al model base i de forma aleatòria per als elements afegits damunt del model base.
  - True - Carrega els pesos per a tot al model utilitzant un fitxer amb els pesos d'una sessió d'entrenament anterior
 - **model_to_train** : "ResNet50" o "SEResNet50". Indica el model base a utilitzar en aquest entrenament i sobre el que s'afegiren les capes per a realitzar la classificació visual del sentiment
  
