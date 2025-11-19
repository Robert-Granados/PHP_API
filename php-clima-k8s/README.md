# README 

Sigue estas instrucciones para preparar, construir y desplegar la API de clima en un entorno local basado en Windows.

## 1. Requisitos

- Windows 10/11.
- Docker Desktop instalado y con la opción de **Kubernetes** habilitada.

## 2. Clonar o copiar el proyecto

Desde PowerShell, ubícar en la carpeta donde se quiere guardar el proyecto y ejecuta:

```powershell
git clone https://github.com/Robert-Granados/PHP_API
cd php-clima-k8s
```

## 3. Construir la imagen Docker

Dentro de la carpeta raíz del proyecto (donde está el `Dockerfile`), ejecutar:

```powershell
docker build -t php-clima-api:v1 .
```

## 4. Desplegar en Kubernetes

Asegúrarse de que Kubernetes esté habilitado en Docker Desktop y aplicar el manifiesto incluido:

```powershell
kubectl apply -f k8s-deployment.yaml
```

## 5. Verificar el pod y el servicio

Comprobar que los recursos se estén ejecutando correctamente:

```powershell
kubectl get pods
kubectl get service php-clima-service
```

## 6. Probar la API en el navegador

Abrir el navegador y visitar:

```
http://localhost:30080
```

Se Debería ver la respuesta expuesta por el servicio PHP desplegado en Kubernetes.
