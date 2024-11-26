Ось як можна оформити ваш текст для GitHub у форматі `README.md`:

```markdown
# Glacier Verifier Node

Детальна інструкція зі встановлення та налаштування Glacier Verifier Node.

## Попередні кроки

1. **Створіть новий EVM-гаманець.**
2. **Отримайте токени з крану BSC Chain Testnet:**
   [BSC Testnet Faucet](https://www.bnbchain.org/en/testnet-faucet)
3. **Зробіть брідж на мережу opBNB Testnet:**
   [opBNB Testnet Bridge](https://opbnb-testnet-bridge.bnbchain.org/deposit)

---

## Встановлення Docker

1. **Завантажте скрипт для встановлення Docker:**
   ```bash
   curl -fsSL https://get.docker.com -o get-docker.sh
   ```

2. **Встановіть Docker:**
   ```bash
   sudo sh get-docker.sh
   ```

3. **Перевірте версію Docker:**
   ```bash
   docker --version
   ```

---

## Запуск Glacier Verifier Node

1. **Запустіть скрипт:**
   ```bash
   docker run -d -e PRIVATE_KEY=$YOUR_PRIVATE_KEY --name glacier-verifier docker.io/glaciernetwork/glacier-verifier:v0.0.2
   ```
   > Замініть `$YOUR_PRIVATE_KEY` на приватний ключ створеного гаманця.

2. **Перегляд логів:**
   ```bash
   docker logs -f glacier-verifier
   ```

---

## Оновлення ноди

1. **Зупиніть та видаліть поточну ноду:**
   ```bash
   docker stop glacier-verifier
   docker rm glacier-verifier
   ```

2. **Перевірте наявність нових версій:**
   [Glacier Labs Node Releases](https://github.com/Glacier-Labs/node-bootstrap/releases)

3. **Завантажте нову версію:**
   ```bash
   docker pull docker.io/glaciernetwork/glacier-verifier:v0.0.2
   ```

4. **Запустіть нову версію:**
   ```bash
   docker run -d -e PRIVATE_KEY=$YOUR_PRIVATE_KEY --name glacier-verifier docker.io/glaciernetwork/glacier-verifier:v0.0.2
   ```

---
