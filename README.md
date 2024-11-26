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

## Корисні посилання
- [Офіційний GitHub репозиторій Glacier Labs](https://github.com/Glacier-Labs/node-bootstrap)

---

Додай цей файл до репозиторія під назвою `README.md`. Якщо потрібна допомога з розміщенням файлу чи налаштуванням репозиторія, дай знати!
