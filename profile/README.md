# TPP-Grupo158

## [Front end](https://github.com/TPP-Grupo158/frontend)
### Requerimientos
- [Docker](https://www.docker.com/)
- [NPM](https://www.npmjs.com/)
### Ejecuccion
  ```
npm run dev
```

o usando docker

```
docker compose -f docker-compose.dev.yml up --build
```
## [Api gateway](https://github.com/TPP-Grupo158/api-gateway)
### Requerimientos
- [Docker](https://www.docker.com/)
- Container de User backend y Image processing Backend levantados
### Ejecuccion
```
docker compose -f docker-compose.yml up --build
```
## [User backend](https://github.com/TPP-Grupo158/user-backend)
### Requerimientos
- [Docker](https://www.docker.com/)
### Ejecuccion
```
docker compose -f docker-compose.yml up --build
```
## [Image processing Backend](https://github.com/TPP-Grupo158/image_processing_backend)
### Requerimientos
- [Docker](https://www.docker.com/)
- 1 o mas GPUS nvidia si se quiere utlizar gpu para las predicciones
- por lo menos 10 gb de memoria libres
- Para que las predicciones sean acessibles publicamente es necesarios hacer los siguiente:
```
docker exec -it minio mc config host add myminio http:/minio:9000 your-access-key your-secret-key
docker exec -it minio-server mc anonymous set download local/medical-images
```
### Ejecuccion
```
docker compose -f docker-compose.yml up --build
```
## [Aneurysm detection service](https://github.com/TPP-Grupo158/Aneurysm-prediction-service)
### Requerimientos
- [Docker](https://www.docker.com/)
- Container Image processing Backend levantado
- 1 o mas GPUS nvidia
- pro lo menos 16 gb de memoria libres
- los siguinetes deep learning models:
  - [VESSEL ROI SEGGMENTATION](https://www.kaggle.com/models/pengchengshi/dataset180_2d_vessel_box_seg_stable)
  - [ANEURYSM CLS 1 Y 2](https://www.kaggle.com/models/pengchengshi/rsna2025-stage2-models)
  - [PLANE 2D CLS](https://drive.google.com/drive/folders/1puJUTLiNyoqLPx3gLVY0yFrcjj493vDV?usp=sharing)
### Ejecuccion
```
docker compose -f docker-compose.yml up --build
```
