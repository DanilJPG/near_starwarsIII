# near_starwarsIII
## Установка и выполнение челленджей 
![image](https://user-images.githubusercontent.com/57448493/182021927-a113739e-fc68-418a-9d8b-d524b97444cc.png)
#### Near Protocol запускает третий эпизод тестнета Stake Wars, целью которого является децентрализация сети NEAR, путем привлечение новых валидаторов. Анонсированные награды составляют 50к $NEAR на ноду в мейнете и 500 $NEAR токенов за успешное выполнение всех заданий. Думаю, описывать что такое Near Protocol не имеет смысла, поэтому читаем информацию о тестнете, подаем заявку на участие по https://nearprotocol1001.typeform.com/to/Z39N7cU9?typeform-source=near.org. В данном гайде описано выполнение заданий. Удачи и да прибудет с Вами Web3. 

#### Список заданй: https://github.com/near/stakewars-iii/tree/main/challenges
#### Форма с выполнением КАЖДОЙ задачи : https://docs.google.com/forms/d/e/1FAIpQLScp9JEtpk1Fe2P9XMaS9Gl6kl9gcGVEp3A5vPdEgxkHx3ABjg/viewform

#### Сайт: https://nearcon.org/
#### Discord : https://discord.gg/bca7SHNM
#### Twitter : https://twitter.com/nearprotocol
### Ссылка на Hetznet : https://hetzner.cloud/?ref=NY9VHC3PPsL0  

### Установка на сервер и инициализация
#### Рекумендуемые параметры сервера: CPU: 4-Core, RAM: 8GB DDR4, Storage: 500GB SSD
#### Сервер на котором бцдц работать:CPU: 8-Core, RAM: 16GB DDR4, Storage: 240GB SSD 
![image](https://user-images.githubusercontent.com/57448493/182022708-27d272e1-1c2b-46f8-a0d4-c2624dc4e15d.png)
#### Стоимость 26,88 Эвро. Главное следить за использзованием  вашей памяти.

### Процесс выбора сервера на Hetzner:

#### 1)Выбираем имя для нашего проекта
![image](https://user-images.githubusercontent.com/57448493/182022753-0d34cf62-a31a-4099-8e96-df27fcf5b65e.png)

#### 2) Выбираем конфигурацию сервера:
![image](https://user-images.githubusercontent.com/57448493/182022795-7847f2ff-48eb-4c63-8408-848623132193.png)
![image](https://user-images.githubusercontent.com/57448493/182022820-05a47a12-4f7b-41f7-a06b-c41e32b823c7.png)

#### 3) Скачиваем MobaExterm
![image](https://user-images.githubusercontent.com/57448493/182022908-ee96955d-3bb4-4412-a2ae-8a6385e54229.png)

#### 4) Выполняем установку и заходим, переходим в Session,выбираем вкладку SSH, в remote host вводим наш IP адрес который пришел нам на почту,которую мы регистрировали
![image](https://user-images.githubusercontent.com/57448493/182022996-3f26c0d9-4436-430c-8873-9bbd8959c110.png)
![image](https://user-images.githubusercontent.com/57448493/182023082-4d1c6a95-ff54-4fda-b316-e853094ec1b2.png)

#### 5) Логинимся:вводим имя root,ввводим пароль который указан в письме, создаем новый пароль
![image](https://user-images.githubusercontent.com/57448493/182023165-1f204414-1c35-4407-b5a3-ba2160f91910.png)
![image](https://user-images.githubusercontent.com/57448493/182023172-f8803754-2ce2-4c03-9a6c-ae03ba74fb1d.png)
![image](https://user-images.githubusercontent.com/57448493/182023184-0c5a4cad-a7bb-4cc1-ab63-41e18c961ed1.png)
![image](https://user-images.githubusercontent.com/57448493/182023192-91c440ca-94e3-43d4-9e43-2134ee059113.png)

### 6) Перед началом работы вы можете убедиться, что на вашем компьютере установлены правильные функции процессора(ожидаем Supported):
```
lscpu | grep -P '(?=.*avx )(?=.*sse4.2 )(?=.*cx16 )(?=.*popcnt )' > /dev/null \
  && echo "Supported" \
  || echo "Not supported"
```

### 7) Обновляем систему:
```
sudo apt update && sudo apt upgrade -y
```

### 8) Устанавливаем инструменты разработчика, Node.js, npm и другие необходимые пакеты
```
sudo apt install -y git binutils-dev libcurl4-openssl-dev zlib1g-dev libdw-dev libiberty-dev cmake gcc g++ python docker.io protobuf-compiler libssl-dev pkg-config llvm cargo
sudo apt install clang build-essential make
sudo apt install curl jq
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -  
sudo apt install nodejs
PATH="$PATH"
```

### 9) Установить NEAR-CLI
#### Вот репозиторий Github для NEAR CLI.: https://github.com/near/near-cli . Для установки NEAR-CLI, если вы не вошли в систему с правами root, что не рекомендуется, вам нужно будет использовать sudoдля установки NEAR-CLI, чтобы сохранить двоичный файл near в /usr/local/bin
```
sudo npm install -g near-cli
```

### 10) Настраиваем окружение. Текущий тестнет проходит в сети shardnet. Вводим название сети в качестве переменной
```
export NEAR_ENV=shardnet
echo 'export NEAR_ENV=shardnet' >> ~/.bashrc
```
#### Вы также можете выполнить эту команду, чтобы установить постоянную среду Near testnet:
```
echo 'export NEAR_ENV=shardnet' >> ~/.bashrc
echo 'export NEAR_ENV=shardnet' >> ~/.bash_profile
source $HOME/.bash_profile
```
#### Можно проверить корректную работу Near-CLI выполнив:
#### Руководство по командам CLI РЯДОМ:
#### Предложения
#### Предложение от проверяющего указывает, что он хотел бы войти в набор проверяющих, для того, чтобы предложение было принято, оно должно соответствовать минимальной цене места.

#### Команда:
```
near proposals
```
#### Текущие валидаторы
#### Здесь отображается список активных валидаторов в текущую эпоху, количество произведенных блоков, ожидаемое количество блоков и скорость онлайн. Используется для мониторинга, если у валидатора возникают проблемы.

#### Команда:
```
near validators current
```
#### Валидаторы следующие
#### Здесь показаны валидаторы, предложение которых было принято одну эпоху назад, и которые войдут в набор валидаторов в следующую эпоху.

#### Команда:
```
near validators next
```

### 11) sudo apt install python3-pip
```
USER_BASE_BIN=$(python3 -m site --user-base)/bin
export PATH="$USER_BASE_BIN:$PATH"
```

### 12) Устанавливаем Rust и установка Building env
```
#### устанавливаем необходимые пакеты
sudo apt install curl build-essential gcc make -y

#### загружаем установочный скрипт Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
#### Вы увидите следующее:
#### Выбираем пункт 1) продолжить установку (по умолчанию).
![image](https://user-images.githubusercontent.com/57448493/182024420-7339d623-2e61-4072-ac68-c408f5e59436.png)

#### активируем среду Rust для текущей оболочки
source ~/.profile
source ~/.cargo/env
```

### 13) Заходим по ссылке https://wallet.shardnet.near.org/ и создаем кошелек NEAR для тестовой сети. Сохраняем мнемонику в надежном месте. Запоминаем имя кошелька, он же Account_ID.
![image](https://user-images.githubusercontent.com/57448493/182023611-9f7ad21f-472f-43ce-8040-b47ef30c63cb.png)
### Клонируем репозиторий с нодой
```
git clone https://github.com/near/nearcore
cd nearcore
git fetch
```
#### Проверяем коммит. По состоянию на 31 июля, актуальный коммит - c1b047b8187accbf6bd16539feb7bb60185bdc38. Актуальный коммит можно найти по ссылке https://github.com/near/stakewars-iii/blob/main/commit.md
```
git checkout c1b047b8187accbf6bd16539feb7bb60185bdc38
```

### 14) Скомпилировать 'nearcore' двоичный файл
```
cargo build -p neard --release --features shardnet
```

#### Двоичный путь является 'target/release/neard'. Если вы видите проблемы, возможно, команда cargo не найдена. Компиляция 'nearcore' двоичного файла может занять некоторое время(у меня заняло примерно час).

### 15) Инициализируем ноду и загружаем генезис файл
```
./target/release/neard --home ~/.near init --chain-id shardnet --download-genesis
```
![image](https://user-images.githubusercontent.com/57448493/182024492-eeab1132-013f-469f-a41f-b90be40879c6.png)

#### Эта команда создаст структуру каталогов и создаст 'config.json' , 'node_key.json' , и 'genesis.json' в сети, которую вы передали.

+ 'config.json' - Параметры конфигурации, которые реагируют на то, как будет работать узел. 'Config.json' содержит необходимую информацию для запуска узла в сети, как взаимодействовать с одноранговыми узлами и как достичь консенсуса. Хотя некоторые параметры настраиваются. Как правило, валидаторы предпочитают использовать файл 'config.json' по умолчанию.

+ 'genesis.json' - Файл со всеми данными, с которыми начиналась сеть в 'genesis'. Здесь содержатся начальные учетные записи, контракты, ключи доступа и другие записи, которые представляют начальное состояние блокчейна. Файл 'genesis.json' представляет собой снимок состояния сети в определенный момент времени. В контактах учетные записи, балансы, активные валидаторы и другая информация о сети.

+ 'node_key.json' - Файл, содержащий открытый и закрытый ключи для узла. Также включает необязательный 'account_id' параметр, который требуется для запуска узла проверки (не рассматривается в этом документе).

+ 'data/' - Папка, в которую 'NEAR' узел будет записывать свое состояние.

## Рекомендую сохранить данные файлы, чтобы потом не возникло проблем с восстановлением и предоставлением данных, что вы действительно все сделали правильно и получили вознаграждения

### 16) Замените config.json
#### Из сгенерированных 'config.json' есть два параметра для изменения:

'boot_nodes': Если вы не указали загрузочные узлы для использования во время инициализации на шаге 3, сгенерированный 'config.json' массив покажет пустой массив, поэтому нам нужно будет заменить его полным массивом с указанием загрузочных узлов.
'tracked_shards': В сгенерированном 'config.json' это поле является пустым. Вам нужно будет заменить его на "tracked_shards": [0]

```
rm ~/.near/config.json
wget -O ~/.near/config.json https://s3-us-west-1.amazonaws.com/build.nearprotocol.com/nearcore-deploy/shardnet/config.json
```

### 17) Запустите узел
```
cd ~/nearcore
./target/release/neard --home ~/.near run
```
![image](https://user-images.githubusercontent.com/57448493/182025977-2ea06a3a-8c71-4718-9381-eb1e82ee368c.png)
### Теперь узел запущен, и вы можете видеть выходные данные журнала в своей консоли. Ваш узел должен находить одноранговые узлы, загружать заголовки до 100%, а затем загружать блоки.
### 18) Активация узла в качестве средства проверки

#### Авторизовать кошелек локально
#### Для подписи транзакций через NEAR-CLI необходимо локально установить ключ полного доступа.

#### Вам нужно выполнить эту команду:
```
near login
```
#### Примечание: Эта команда запускает веб-браузер, позволяющий авторизовать полный ключ доступа для локального копирования.

1 – Скопируйте ссылку в свой браузер
изображение
![image](https://user-images.githubusercontent.com/57448493/182026199-228db273-b4f8-4fe6-995b-239794ef70a3.png)

2 – Предоставить доступ к Near CLI
![Screenshot_2](https://user-images.githubusercontent.com/57448493/182026211-077f6e98-7c45-488e-b0a9-1a21ffb87ccd.png)

3 – После предоставления разрешения вы увидите страницу, подобную этой, вернитесь в консоль
![image](https://user-images.githubusercontent.com/57448493/182026231-5a6bbb0b-d962-43b2-978b-2d868a5a15f5.png)
#### Должно быть так ![image](https://user-images.githubusercontent.com/57448493/182026277-f32d7a25-6254-47a8-ac89-793e9bf43a64.png)
#### если возникла такая ошибка, попробуйте сделать снепшот genesis.json, командой 
```
cd ~/.near
wget https://s3-us-west-1.amazonaws.com/build.nearprotocol.com/nearcore-deploy/shardnet/genesis.json
```
![image](https://user-images.githubusercontent.com/57448493/182026311-ac58eef7-b1f8-48b6-9a9f-0dd380f77de4.png)

Вообще советую не здаваться,у меня получилось привязать с раза 20го, так что пробуйте

#### Проверьте validator_key.json
 Выполните следующую команду:
```
cat ~/.near/validator_key.json
```
#### Примечание: Если файл validator_key.json отсутствует, выполните следующие действия, чтобы создать его
Создать validator_key.json

Сгенерируйте файл ключа:
```
near generate-key <pool_id>
```
#### <pool_id> ---> xx.factory.shardnet.near ГДЕ xx - это имя вашего пула

### Скопируйте сгенерированный файл в папку shardnet: не забудьте заменить <pool_id> идентификатором вашей учетной записи
```
cp ~/.near-credentials/shardnet/YOUR_WALLET.json ~/.near/validator_key.json
```
#### Отредактируйте 'account_id' => xx.factory.shardnet.near, где xx - это имя вашего пула

#### Изменить private_keyна secret_key
Примечание: идентификатор учетной записи должен совпадать с именем контракта пула ставок, иначе вы не сможете подписывать блоки.\

Содержимое файла должно быть в следующем формате:
```
{
  "account_id": "xx.factory.shardnet.near",
  "public_key": "ed25519:HeaBJ3xLgvZacQWmEctTeUqyfSU4SDEnEwckWxd92W2G",
  "secret_key": "ed25519:****"
}
```
### 19)Создаем сервисный файл
```
sudo tee /etc/systemd/system/neard.service > /dev/null <<EOF
[Unit]
Description=neard

[Service]
Type=simple
User=root
#Group=near
WorkingDirectory=/home/root/.near
ExecStart=/home/<USER>/nearcore/target/release/neard run
Restart=on-failure
RestartSec=30
KillSignal=SIGINT
TimeoutStopSec=45
KillMode=mixed

[Install]
WantedBy=multi-user.target
EOF
```
#### Start
Команда:
```
sudo systemctl enable neard
```
Команда:
```
sudo systemctl start neard
```
#### Если вам необходимо внести изменения в сервис из-за ошибки в файле. Он должен быть перезагружен:
```
sudo systemctl reload neard
```
#### Смотреть журналы
Команда:
```
journalctl -n 100 -f -u neard
```
#### Сделайте вывод журнала красивым шрифтом

Команда:
```
sudo apt install ccze
```
#### Просмотр журналов с цветом

Команда:
```
journalctl -n 100 -f -u neard | ccze -A
```
### Стать валидатором
Чтобы стать валидатором и войти в набор валидаторов, необходимо выполнить минимальный набор критериев успеха.

1)Узел должен быть полностью синхронизирован
#### Проверяем синхронизацию
```
curl -s http://127.0.0.1:3030/status | jq .sync_info
```
![image](https://user-images.githubusercontent.com/57448493/182026956-df2c1f76-c39a-42b1-ba9c-64ca3e749e88.png)

2) 'validator_key.json' должнн быть на месте
3)Контракт должен быть инициализирован с помощью public_key в validator_key.json
4) Идентификатор учетной записи должен быть установлен на идентификатор контракта пула ставок
5) Должно быть достаточно делегаций, чтобы соответствовать минимальной цене места. Посмотреть стоимость места можно здесь(https://explorer.shardnet.near.org/nodes/validators).
6) Предложение должно быть отправлено путем пинга контракта
7) После принятия предложения валидатор должен подождать 2-3 эпохи, чтобы войти в набор валидаторов
8) После установки валидатора валидатор должен выдавать более 90% назначенных блоков
9) Проверьте состояние работы узла проверки. Если отображается “Валидатор”, ваш пул будет выбран в текущем списке валидаторов.
 
### Создаем пул ставок 
NEAR использует фабрику пула ставок с контрактом на ставки, внесенным в белый список, для обеспечения сохранности средств делегаторов. Чтобы запустить валидатор на NEAR, пул ставок должен быть развернут на учетной записи NEAR и интегрирован в узел NEAR validator. Делегаторы должны использовать пользовательский интерфейс или командную строку, чтобы сделать ставку на пул. Пул ставок - это смарт-контракт, который развертывается на учетной записи NEAR.

#### Развертывем пул ставок командой

### Важно! заменяем `<pool id>` , `<MONIKER>` и `<ACCOUNT_ID>` . Вместо `<public key>` вставляем ключ из файла validator_key.json
```
near call factory.shardnet.near create_staking_pool '{"staking_pool_id": "<pool id>", "owner_id": "<accountId>", "stake_public_key": "<public key>", "reward_fee_fraction": {"numerator": 5, "denominator": 100}, "code_hash":"DD428g9eqLL8fWUxv8QSpVFzyHi1Qd16P8ephYCTmMSZ"}' --accountId="<accountId>" --amount=30 --gas=300000000000000
```
### Теперь можем застейкать еще токенов. В моем случае 30(минимум)
#### Должно быть примерно так
```
NEAR_ENV=shardnet near call $POOL deposit_and_stake --amount 30 --accountId $ACCOUNT_ID --gas=300000000000000
```
![image](https://user-images.githubusercontent.com/57448493/182249593-d65e712f-0da0-47ae-a6ea-97d32e5994e0.png)

#### Мониторинг 
Заходим по ссылке и ищем нашего валидоатор и проверяем количество застейканных монет:
https://explorer.shardnet.near.org/nodes/validators
![image](https://user-images.githubusercontent.com/57448493/182044145-8a5c91a3-b8d4-4f64-8de0-63683432b5d1.png)
