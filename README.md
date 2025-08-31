# DEVOPS-CLOUD-CP04
Implementar a migração completa para ACR e ACI 

## 🔧 Passo 1 — Login no ACR

Primeiro garante que você tá autenticado no ACR:

```bash
az acr login --name acrminilab367
```

---

## 🔧 Passo 2 — Build da imagem

Na pasta onde está teu `Dockerfile`, roda:

```bash
docker build -t datalk-api:v1 .
```

Isso cria a imagem local com a tag `datalk-api:v1`.

---

## 🔧 Passo 3 — Tag para o ACR

Agora precisamos taguear a imagem local com o endereço do ACR:

```bash
docker tag datalk-api:v1 acrminilab367.azurecr.io/datalk-api:v1
```

---

## 🔧 Passo 4 — Push para o ACR

Envia pro teu repositório do ACR:

```bash
docker push acrminilab367.azurecr.io/datalk-api:v1
```

---

## 🔧 Passo 5 — Conferir no ACR

Pra confirmar que subiu:

```bash
az acr repository list --name acrminilab367 --output table
```

Você deve ver algo como:

```
Result
---------
datalk-api
```

az acr import \
  --name acrminilab367 \
  --source docker.io/library/mongo:6.0 \
  --image mongo:6.0
