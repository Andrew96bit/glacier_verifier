# Glacier Verifier Node Setup

## Попередні вимоги

### 1. Створіть новий EVM-гаманець
- Використовуйте будь-який зручний вам крипто-гаманець.
- Для отримання тестових монет використовуйте **[кран BSC Chain Testnet](https://www.bnbchain.org/en/testnet-faucet)**.

### 2. Зробіть брідж на opBNB Testnet
- Використовуйте **[opBNB Testnet Bridge](https://opbnb-testnet-bridge.bnbchain.org/deposit)** для бріджу тестових токенів.

---

## Встановлення Docker

### 1. Завантажте скрипт для встановлення Docker
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
```

### 2. Встановіть Docker
```bash
sudo sh get-docker.sh
```

### 3. Перевірте версію Docker
```bash
docker --version
```

---

## Запуск Glacier Verifier

### 1. Запуск скрипта
```bash
docker run -d -e PRIVATE_KEY=$YOUR_PRIVATE_KEY --name glacier-verifier docker.io/glaciernetwork/glacier-verifier:v0.0.2
```
**Замініть `$YOUR_PRIVATE_KEY` на приватний ключ створеного EVM-гаманця.**

### 2. Перегляд логів
```bash
docker logs -f glacier-verifier
```

#### Додаткова інформація
- Мережа складається з понад **10 000 активних нод**, з яких лише **200 обираються кожні п’ять хвилин**.  
- Тому статус вашої ноди оновиться через певний час, приблизно **30 хвилин**.  
- Перевірити статус ноди можна тут: **[Glacier Node Status](https://testnet.nodes.glacier.io/status)**.

---

## Оновлення ноди

### 1. Зупиніть і видаліть стару версію
```bash
docker stop glacier-verifier
docker rm glacier-verifier
```

### 2. Завантажте останню версію
Останні версії доступні на **[GitHub Releases](https://github.com/Glacier-Labs/node-bootstrap/releases)**.
```bash
docker pull docker.io/glaciernetwork/glacier-verifier:v0.0.2
```

### 3. Перезапустіть ноду
```bash
docker run -d -e PRIVATE_KEY=$YOUR_PRIVATE_KEY --name glacier-verifier docker.io/glaciernetwork/glacier-verifier:v0.0.2
```

---
