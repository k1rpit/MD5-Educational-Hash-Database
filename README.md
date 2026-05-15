# MD5-Educational-Hash-Database
[Educational] Учебная база простых MD5 хэшей (hash|password format) для изучения криптографии &amp; security auditing.
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
 ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)
 
 
t.me/k1rpit718s
https://web.telegram.org/k/#@geiporno718s
# ⚡ MD5 Educational Hash Database (hash_pw_baza.txt)

[RU] 
Учебный текстовый словарь простых MD5-хэшей и паролей. Выложен исключительно в образовательных целях: для изучения криптографии, лавинного эффекта, чувствительности алгоритмов к регистру (case-sensitivity) и тестирования локальных дехэшеров.

[EN] 
Educational raw text wordlist of simple MD5 hashes and passwords. This file is published strictly for educational purposes: studying cryptography, the avalanche effect, case-sensitivity research, and testing local crack-tools.

---

## 📊 Формат словаря / Wordlist Format

Текстовый файл `hash_pw_baza.txt` использует чистый и универсальный формат с разделителем `|` (pipe). Никаких лишних пробелов. Полная совместимость с любыми скриптами (Python, Go, C++) и утилитами для аудита (Hashcat, John the Ripper).

```text
<MD5-хэш>|<исходный_пароль>
```

### Примеры внутри словаря / Examples inside:
* **Default accounts:** `admin`, `root`, `msfadmin`
* **Case-sensitivity test:** Разные хэши для `root`, `Root` и `ROOT`.
* **Mirrored digits:** `1234` / `4321`, `1234567890` / `0987654321`

---

## 🛠️ Чтение словаря в Python / How to read this wordlist with Python

Вы можете легко прочитать этот текстовый файл в своем скрипте-дехэшере с помощью следующего кода:

```python
def lookup_hash(target_hash):
    # Очищаем ввод от пробелов и приводим к нижнему регистру
    target_hash = target_hash.strip().lower()
    
    with open("hash_pw_baza.txt", "r", encoding="utf-8") as f:
        for line in f:
            if "|" in line:
                h_key, password = line.strip().split("|", 1)
                if h_key == target_hash:
                    return password
    return None
```

---

## 📜 Лицензия / License

This wordlist is dedicated to the public domain under the **Unlicense**. Полная свобода действий. Вы можете копировать, изменять, распространять и использовать этот текстовый файл в любых своих утилитах без каких-либо ограничений и обязательств.

_Created by k1rpit_
