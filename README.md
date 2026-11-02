# ibot2 Tiles Survive

<img width="1000" height="83" alt="image" src="https://github.com/user-attachments/assets/e9b9a1a5-940b-4e31-8979-06fdb912b855" />
# ibot2 — Tiles Survive Auto Bot

[Русский](#русский) · [English](#english) · [Скачать](https://ibot2.ru/#download) · [Releases](https://github.com/1gaSPb/Tiles-Survive-Auto-Bot/releases/latest) · [Поддержка](https://t.me/ibot2_ts)

## Русский

ibot2 выполняет повторяющиеся действия в окне Tiles Survive на Windows. Вы выбираете задачи на ПК и при желании управляете ими с телефона через Telegram.

Справка сверена с текущим кодом **2.5.0.7**. Сервер может выдавать другой публичный или тестовый выпуск — смотрите версию внизу окна. [Подробные инструкции по задачам](docs/TELEGRAM_UPDATE.md).

### Что умеет ibot2

- **База:** «Руки (помощь)», книги, конверты и подарки жителей, лечение, сбор угля по таймеру, «Ловить яйца» по видимой игровой иконке.
- **Рейды и бои:** вступление в рейды, выбор бродячих и событийных рейдов; отдельные режимы «Бить зомби» и «Создавать рейды». Есть автостарт по порогу энергии и лимит действий за сессию.
- **Ресурсы:** пять маршей с назначением «Рейды», «Еда», «Древесина», «Металл» или «Топливо». Сбор с плит, переотправка через 45 минут–12 часов с шагом 15 минут, кнопки «Обновить сбор» и «Отозвать».
- **Рудник:** уровни 2–6 или «Авто (все)», обновление по таймеру, поиск места. После успешного занятия уровня 5/6 интервал не короче 45 минут. Telegram сообщает о занятии вашим отрядом и следующем обновлении.
- **Дополнительно:** питомцы и выбор яиц, VIP-награды, технологии альянса, подарки союза и с зомби, ресурсы с электростанции, обновление автоприсоединения, усиление сбора 50%/100%.
- **Telegram-пульт:** статус, старт/пауза/стоп, доступные настройки, скриншоты игры и ibot2, марши, перезапуск игры/приложения, уведомления, подписка и реферальная программа.
- **Восстановление:** возврат на базу, обработка некоторых ошибок, переподключение после входа с другого устройства и «Анти-зависание». Перезапуск игры из пульта требует подходящей команды запуска; восстановление после любого вылета не гарантируется.

Зомби и создание рейдов — взаимоисключающие спецрежимы: обычные задачи базы приостанавливаются; приоритетное обновление рудника может выполняться. Во время отзыва и отправки на сбор другие задачи ждут завершения цикла.

При включённом автозапуске зомби автосоздание рейдов ждёт достижения лимита зомби; нулевой лимит зомби блокирует автоматический переход к созданию рейдов.

Технологии альянса расходуют игровые ресурсы, электростанция — её очки. Покупки энергии и усиления за алмазы разрешаются отдельно; банки энергии и ежедневный бонус тоже настраиваются отдельно.

### Антибан

В интерфейсе есть **два разных элемента**.

**«Антибан» — сетевые ограничения Windows.** При запуске нового цикла через «Старт» приложение включает и проверяет правило брандмауэра, маршруты для заданных сетей и записи hosts. Нажатие круглого индикатора в шапке повторяет операцию. Зелёный цвет означает успех четырёх проверок; красный — состояние не проверено, проверка идёт или не все проверки прошли. Подробности — при наведении и в логах.

Изменения затрагивают весь ПК и могут влиять на другие приложения. Брандмауэр и hosts остаются после закрытия бота; маршруты могут потребовать повторного включения после перезагрузки или смены сети. Кнопки отмены нет. Красный индикатор сам по себе не запрещает автоматизацию.

**«Анти-детект» — механизмы снижения шаблонности поведения.** Чекбокс находится в «Управление» → «Доп. функции». Он меняет часть задержек и движение курсора, добавляет 5–45 секунд к интервалу рудника и сдвигает часовой интервал угля в пределах ±5 минут. Быстрые сценарии имеют исключения; это не смещение каждого клика.

Пользователь меняет чекбокс и «Задержка нажатий»; диапазоны случайности задаёт код. По умолчанию «Анти-детект» выключен, задержка — 0,30 секунды. Это исходные значения, а не доказанная безопасная рекомендация. Автоматических перерывов и ограничения длительности всей сессии нет.

**Автоматизация игры потенциально может нарушать правила игры. Антибан-функции снижают шаблонность действий, но не могут гарантировать отсутствие санкций со стороны игры.** Сетевые проверки также не дают такой гарантии.

### Быстрый старт

1. [Скачайте ibot2.exe](https://ibot2.ru/#download) или откройте [Releases](https://github.com/1gaSPb/Tiles-Survive-Auto-Bot/releases/latest). Запустите игру и войдите в аккаунт.
2. Запустите ibot2 от имени администратора с интернетом. На новом ПК пробный день запрашивается автоматически. Если показано окно активации, используйте действующий ключ.
3. В «Управление» включите нужные задачи и назначьте марши. Функции «Дополнительно» выбираются отдельно. Остальные значения для первой проверки можно оставить исходными.
4. Оставьте игру видимой. Стандарт игровой области — **687×895**; бот подгоняет размер при запуске и старте. Если окно не найдено — [инструкция привязки](docs/TELEGRAM_UPDATE.md#привязка-окна-игры).
5. Нажмите «Старт»: также применяются сетевые ограничения Windows, описанные выше. Проверьте действия и подсказку индикатора. «Пауза» меняется на «Продолжить», «Стоп» завершает цикл.
6. При желании нажмите «Управление через Telegram» внизу окна и выполните привязку по QR, ссылке или коду.

### Управление

- **«Управление»:** задачи базы, задержка, рудник, рейды, пять маршей, сбор с плит, «Доп. функции», старт/пауза/стоп и «Трата энергии».
- **«Дополнительно»:** питомцы, награды, альянс, усиление сбора. Выполняются после «Старт».
- **Клик по номеру версии:** «Отладка (пороги и окно эмулятора)» — неизвестное окно, размер, пороги, горячие клавиши, команда перезапуска, настройки рудника. «Показывать окно логов» открывает отдельное окно; «Расширенные логи» добавляет подробности. Вкладки «Логи» нет.

По умолчанию **F1** — старт, **F2** — пауза/продолжение, **F3** — стоп, **F5** — зомби, **F6** — создание рейдов. В отладке можно изменить назначения и включить Shift.

**F9** запускает первый сохранённый макрос на один цикл или останавливает его. Кнопки открытия редактора записи в текущем главном окне нет. [Ограничения макросов](docs/TELEGRAM_UPDATE.md#макросы).

### Telegram

Откройте [@ibot2tobi_bot](https://t.me/ibot2tobi_bot) через окно привязки. **/panel** открывает Mini App, **/licenses** и **/use** выбирают устройство.

Основные команды: **/run**, **/pause**, **/stop**, **/status**, **/settings**, **/set**, **/marches**, **/gather**, **/recall**, **/screenshot_game**, **/screenshot_ibot2**. **/start** открывает бота/привязку, а не запускает автоматизацию. Пульт также включает спецрежимы, перезапуск игры и ibot2, продление и реферальный раздел.

Уведомления: занятие рудника, отправка/возврат со сбора, выключение спецрежимов, результаты перезапуска, приближение конца подписки. Доступны основные настройки базы, рейдов, рудника, маршей и энергии. Настройки вкладки «Дополнительно», сетевого «Антибан» и локальной отладки текущий пульт не передаёт.

[Подключение, все команды и примеры](docs/TELEGRAM_UPDATE.md#telegram-пульт). ПК, игра и ibot2 должны оставаться включёнными, с интернетом и доступным окном игры.

### Требования

- Windows 10/11, права администратора, интернет для первого запуска, лицензии, обновлений и Telegram.
- Официальный ПК-клиент либо совместимый эмулятор. Встроенный поиск: TilesSurvive, LDPlayer, MSI App Player; другой заголовок задаётся в отладке. Совместимость с любым эмулятором не гарантируется.
- Доступный рабочий стол и видимая игровая область: не сворачивайте и не перекрывайте игру, не блокируйте сеанс.
- Sandboxie необязателен; для песочницы нужны проверка заголовка и корректная команда запуска.
- Готовый exe не требует Python. Свой размер и отключение подгонки доступны в отладке; 687×895 — игровая область, не разрешение экрана.

### FAQ

**Нужно ли настраивать антибан? Гарантирует ли он отсутствие блокировки?**  
Сетевые настройки применяются при «Старт» и по нажатию индикатора. «Анти-детект» включается отдельно. Можно начать с исходных настроек, но ни один режим не гарантирует отсутствие санкций.

**Можно ли управлять с телефона? Нужно ли держать ПК включённым?**  
После установки и привязки — через пульт. Автоматизация выполняется на включённом ПК.

**Ошибка привязки окна — что делать?**  
Откройте игру, проверьте права и размер. Кликните версию → точный заголовок → «Применить» → «Проверить». Встроенные клиенты имеют приоритет: закройте лишние окна. [Подробности](docs/TELEGRAM_UPDATE.md#привязка-окна-игры).

**Что делать после обновления?**  
Полностью закройте и снова запустите ibot2: обычный загрузчик получает модули при запуске. При необходимости скачайте новый exe с сайта/Releases. Настройки хранятся в `%APPDATA%\ibot2\settings.json`; изменённые вручную пороги сохраняют приоритет над новыми значениями версии. Проверьте задачи; при обычном обновлении не удаляйте настройки и лицензию.

**Бот ошибается или антивирус блокирует файл?**  
Проверьте источник загрузки, версию и окно игры. Включите логи и опишите проблему в [группе](https://t.me/ibot2_ts). Не отключайте защиту Windows вслепую. [Решение проблем](docs/TELEGRAM_UPDATE.md#решение-проблем).

## English

ibot2 automates repetitive actions in the Tiles Survive window on Windows. Choose tasks on your PC and optionally control them from your phone through Telegram.

This guide follows the current **2.5.0.7** source tree. The server may distribute a different public or test build; check the version at the bottom of the app. [Detailed task guides in Russian](docs/TELEGRAM_UPDATE.md).

### What ibot2 can do

- **Base tasks:** alliance help («Руки (помощь)»), books, envelopes and resident gifts, healing, timed coal collection, and catching eggs through the visible game icon.
- **Raids and combat:** join raids, choose wandering and event raids, or use the separate «Бить зомби» (fight zombies) and «Создавать рейды» (create raids) modes. Energy thresholds and per-session action limits are available.
- **Resources:** assign each of five marches to raids, food, wood, metal or fuel. Gather from world tiles, resend every 45 minutes–12 hours in 15-minute steps, refresh gathering or recall troops.
- **Mine:** levels 2–6 or automatic selection, timed refresh and spot search. After successfully occupying level 5/6, the interval is at least 45 minutes. Telegram reports your troop's occupation and next refresh.
- **Additional tasks:** pets and egg selection, VIP rewards, alliance technologies and gifts, power station resources, zombie gifts, auto-join refresh, and 50%/100% gathering boosts.
- **Telegram remote:** status, start/pause/stop, supported settings, game/app screenshots, marches, game/app restart, notifications, renewal and referrals.
- **Recovery:** return to base, handle some errors, reconnect after another-device login, and «Анти-зависание». Remote game restart needs a suitable launch command; recovery from every crash is not guaranteed.

Zombie fighting and raid creation are mutually exclusive special modes. They suspend normal base tasks; priority mine refresh can still run. Other tasks wait while a gathering recall/resend cycle uses the controls.

With automatic zombie mode enabled, automatic raid creation waits for the zombie action limit. A zero zombie limit prevents that automatic switch to raid creation.

Alliance technologies spend game resources; power station collection spends station points. Diamond purchases for energy and gathering boosts require separate permission. Energy items and the daily bonus also have separate settings.

### Anti-ban

There are **two distinct controls**.

**«Антибан» applies Windows network restrictions.** Starting a new loop with «Старт» enables and checks a firewall rule, routes for specified networks and hosts entries. Click the round header indicator to repeat. Green means all four checks passed. Red means unchecked, checking, or a check failed. Hover or open logs for details.

These settings affect the whole PC and may affect other apps. Firewall and hosts changes remain after closing ibot2; routes may need reapplying after a reboot or network change. There is no undo button. A red indicator does not itself prevent automation.

**«Анти-детект» reduces repetitive timing and movement patterns.** Its checkbox is under «Управление» → «Доп. функции». It varies some delays and cursor movement, adds 5–45 seconds to mine intervals and varies hourly coal collection by ±5 minutes. Fast scenarios have exceptions; it does not offset every click.

You can change the checkbox and «Задержка нажатий» (click delay); the code chooses the random ranges. Defaults are off and 0.30 seconds. These are initial values, not a proven safe recommendation. There are no automatic human-style breaks or maximum session-duration setting.

**Game automation may violate the game's rules. Anti-ban features reduce repetitive patterns but cannot guarantee protection from sanctions.** Network checks do not provide that guarantee either.

### Quick start

1. [Download ibot2.exe](https://ibot2.ru/#download) or use [Releases](https://github.com/1gaSPb/Tiles-Survive-Auto-Bot/releases/latest). Open the game and sign in.
2. Run ibot2 as administrator with internet access. A new PC requests a one-day trial automatically. If activation appears, use a valid key.
3. Choose tasks and march assignments on «Управление». Additional tasks are selected on «Дополнительно». Leave other defaults for the first check.
4. Keep the game visible. The default **game client area is 687×895**; ibot2 resizes it on launch and start. If detection fails, see the [window guide in Russian](docs/TELEGRAM_UPDATE.md#привязка-окна-игры).
5. Press «Старт». This also applies the Windows network restrictions above. Check game actions and the indicator tooltip. «Пауза» becomes «Продолжить» (resume); «Стоп» ends the loop.
6. Optionally click «Управление через Telegram» at the bottom and link by QR, link or code.

### Controls

- **«Управление» (Control):** base tasks, delay, mine, raids, five marches, gathering, extra options, start/pause/stop and energy rules.
- **«Дополнительно» (Additional):** pets, rewards, alliance tasks and boosts; these run after Start.
- **Click the version:** opens debugging settings for unknown windows, size, recognition thresholds, hotkeys, restart command and mine options. «Показывать окно логов» opens a separate log window; «Расширенные логи» adds detail. There is no Logs tab.

Default hotkeys: **F1** start, **F2** pause/resume, **F3** stop, **F5** zombies, **F6** raid creation. Assignments and a Shift modifier can be changed in debugging settings.

**F9** plays the first saved macro once or stops it. The current main interface has no button to open the recording editor. [Macro limitations in Russian](docs/TELEGRAM_UPDATE.md#макросы).

### Telegram

Open [@ibot2tobi_bot](https://t.me/ibot2tobi_bot) through the linking dialog. **/panel** opens the Mini App; **/licenses** and **/use** choose a device.

Main commands: **/run**, **/pause**, **/stop**, **/status**, **/settings**, **/set**, **/marches**, **/gather**, **/recall**, **/screenshot_game**, **/screenshot_ibot2**. **/start** opens the Telegram bot/linking flow; it does not start PC automation. The panel also offers special modes, game/app restart, renewal and referrals.

Notifications cover mine occupation, gathering departure/return, special modes turning off, restart results and an expiring subscription. Supported settings cover base tasks, raids, mine, marches and energy. The current remote does not transfer Additional-tab tasks, system «Антибан» or local debugging options.

[Linking, all commands and examples in Russian](docs/TELEGRAM_UPDATE.md#telegram-пульт). Keep the PC, game and ibot2 running, with internet and an accessible game window.

### Requirements

- Windows 10/11, administrator rights, and internet for initial setup, licensing, updates and Telegram.
- A running official PC client or compatible emulator. Built-in detection covers TilesSurvive, LDPlayer and MSI App Player. Other titles can be configured; universal compatibility is not guaranteed.
- An accessible desktop and visible game area. Do not minimize or cover the game, or lock the desktop.
- Sandboxie is optional. Sandboxed games need window checks and a suitable restart command.
- The packaged exe does not require Python. Custom sizes and disabling automatic resizing are available; 687×895 is the game area, not your screen resolution.

### FAQ

**Do I need to configure anti-ban? Does it prevent bans?**  
Network settings are applied on Start and when the indicator is clicked. «Анти-детект» is separate. You can begin with defaults, but no mode guarantees protection from sanctions.

**Can I use my phone? Must the PC stay on?**  
After installation and linking, use the remote. Automation still runs on the powered-on PC.

**What if the game window is not detected?**  
Open the game and check permissions and size. Click the version → exact title → «Применить» (apply) → «Проверить» (check). Built-in clients take priority; close extra windows. [Details in Russian](docs/TELEGRAM_UPDATE.md#привязка-окна-игры).

**What should I do after an update?**  
Fully close and reopen ibot2; the normal launcher retrieves modules on startup. Download a new exe when required. Settings remain in `%APPDATA%\ibot2\settings.json`; custom thresholds take priority over updated defaults. Review tasks without deleting settings or the licence.

**What if actions fail or antivirus blocks the file?**  
Check the download source, version and window. Enable logs and describe the issue in the [support group](https://t.me/ibot2_ts). Do not blindly disable Windows protection. [Troubleshooting in Russian](docs/TELEGRAM_UPDATE.md#решение-проблем).

