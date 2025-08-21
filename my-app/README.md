# my-app (Helm Chart)

Chart modular que despliega **frontend**, **backend** y **database (MySQL)** mediante subcharts. Soporta configuraciones por entorno y persistencia de datos con **PVC**.

## Requisitos
- Kubernetes 1.23+
- Helm 3.9+
- StorageClass por defecto (o define `database.persistence.storageClassName`)

## Estructura
- `charts/frontend`, `charts/backend`, `charts/database`: subcharts independientes
- `values.yaml`: valores por defecto
- `values-dev.yaml` / `values-prod.yaml`: ejemplos por entorno

## Uso
```bash
helm lint my-app
helm install my-app ./my-app -f my-app/values-dev.yaml
# o producción:
helm install my-app ./my-app -f my-app/values-prod.yaml
