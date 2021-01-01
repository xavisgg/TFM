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
- **data/resnet50_weights_adam.hdf5:** Pesos del model entrenat basat en l'arquitectura ResNet50 utilitzant l'optimitzador Adam.
- **data/resnet50_fit_hist_adam_part1.npy:** Històric de la primera part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Adam.
- **data/resnet50_fit_hist_adam_part2.npy:** Històric de la segona part de l'entrenament del model basat en Resnet50 utilitzant l'optimitzador Adam.
- **data/seresnet50_weights_adam.hdf5:** Pesos del model entrenat basat en l'arquitectura SEResNet50 utilitzant el optimitzador Adam.
- **data/seresnet50_fit_hist_adam_part1.npy:** Històric de la primera part de l'entrenament del model basat en SEResnet50 utilitzant l'optimitzador Adam.
- **data/seresnet50_fit_hist_adam_part2.npy:** Històric de la segona part de l'entrenament del model basat en SEResnet50 utilitzant l'optimitzador Adam.

## Configuració dels Jupyter Notebooks
### tfm-models-train
Aquest Notebook executa l'entrenament del model sel·leccionat. A més, donada la limitació de sessions continues a Kaggle de 9h com a màxim, el Notebook permet la inicialització dels pesos basat en el dataset _ImageNet_ o bé carregar els pesos d'una sessió anterior per tal de continuar l'entrenament del model. Els paràmetres a modificar en aquest Notebook per tal de triar el comportament desitjat son:

- **continue_training** 
  - False - Inicialitza els pesos de la xarxa amb els pesos del dataset del model pre-entrenat amb el conjunt _ImageNet_ per a la part corresponent al model base i de forma aleatòria per als elements afegits damunt del model base.
  - True - Carrega els pesos per a tot al model utilitzant un fitxer amb els pesos d'una sessió d'entrenament anterior
 - **model_to_train** : "ResNet50" o "SEResNet50". Indica el model base a utilitzar en aquest entrenament i sobre el que s'afegiren les capes per a realitzar la classificació visual del sentiment
  
