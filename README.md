# Tamsa Health: a preventive and functional medicine practice site with a Formgong form

**Live demo:** https://tamsa.formgong.com · Download: the [latest release](https://github.com/formgong/tamsa-template/releases/latest) zip.

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/formgong/tamsa-template) [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fformgong%2Ftamsa-template&project-name=tamsa&repository-name=tamsa)

Each button copies the site to your GitHub and publishes it. Then replace `fk_your_access_key` in `index.html` of your copy with your Formgong access key (free at https://formgong.com/new) and commit: the host republishes on its own.

Сайт практики превентивної та функціональної медицини з формою Формгонг

A bright one-page site for a preventive health or functional medicine practice, in a single `index.html` plus an `img/` folder. The demo practice, Tamsa Health, its team, reviews, prices and address are fictional sample content.

- **Header.** A floating pill with the logo, the menu and a booking button. It is see-through over the hero, turns white once you scroll, hides on the way down and comes back on the way up. On phones it becomes a menu button, and a booking bar appears at the bottom of the screen.
- **Hero.** A dark, full-screen hero where three photos cross-fade with a slow zoom. The headline rises word by word. Three numbers on the right count up above lines that fill in. The hero stays pinned while the next section slides over it.
- **Start here.** Two cards: a free intro call for people who are not sure yet, and a small picker. Choose a goal and it suggests where to begin; "Book this" picks that service in the form.
- **Care.** Five rounded cards: the long check-up with a sample results summary, lab panels, nutrition, coaching, and sleep and stress. Each card's link picks its service in the form.
- **Why us.** A dark section that stays on screen while four short statements change one by one as you scroll, with a counter and a progress line.
- **How a visit works.** Four numbered steps beside a photo with a "next free slot" card. A line fills in and the step dots light up as you scroll.
- **Team.** Four people with portraits, roles and topic tags. On phones the row scrolls sideways.
- **Membership.** Three plans with a monthly/yearly switch.
- **Reviews.** A rating summary and six review cards in a row with arrows.
- **FAQ.** Questions on the right ("Lena from Fairview asks…"), a call button on the left.
- **Book.** A dark section with the appointment request form.
- **Footer.** Address, hours, phone, email and a large wordmark.

Blocks fade up as they scroll into view. Without JavaScript everything is visible and the statements are stacked. With `prefers-reduced-motion: reduce` nothing moves: the hero shows one photo, the statements are stacked and the numbers are shown as they are.

## English

**Set up the form**

1. Create a form in the Formgong dashboard and copy its access key.
2. In `index.html`, replace `fk_your_access_key` with that key.
3. The form sends `name`, `email`, `phone`, `service`, `preferred_time`, `message`, a hidden `subject`, plus `access_key` and the empty `botcheck` spam trap. `name` and `email` are required; phone, best time and the note are optional. `service` is one of: Free intro call, Baseline check-up, Results review, Membership, Nutrition, Coaching.
4. It shows thanks only when Formgong answers `success: true`. If the answer is anything else, it shows the error and keeps what was typed.

**Edit**

- Colours are at the top of the styles: `--ink` for the dark sections and text, `--cobalt` for headings' accent words, links and the blue cards, `--tang` (tangerine) for buttons and highlights, `--sky` for the light page background. Fonts are Fraunces (headings) and Figtree (text).
- Section order in `<main>`: hero, start here, care, statements, how a visit works, team, membership, reviews, FAQ, book.
- The picker options are the radio buttons in `#goals`: `data-title`, `data-text` and `data-service` set what the suggestion says and which service "Book this" picks.
- The statements are the `<li>` items in `.statements`. Add or remove items; the scroll length is set by `.seq { height: 380vh }`.
- Plan prices use `data-m` (monthly) and `data-y` (yearly).
- The hero numbers use `data-count`.
- Replace the photos in `img/`, keeping the file names, or change the paths in `index.html`. The prompts used are in `img-prompts.json`.

**Images.** The twelve photos were generated for this template with ChatGPT image generation (OpenAI) and saved as WebP. The people and places are fictional. You may use them in your own site, but replace them with photos of your own practice and team before launch.

**Health data.** This form is for appointment requests. Don't use it to collect diagnoses, medical history, prescriptions or insurance numbers; keep those in your clinic's own patient system. The form shows a hint next to the note field: "Please don't include medical details here — we'll talk about them in person."

**Sample content.** The team, reviews, ratings, prices, numbers, address and phone number are examples. Replace them with your own, and don't publish reviews you did not receive.

The "Powered by Formgong" links point to `https://formgong.com/review-page/fk_your_access_key`, so the same find and replace covers them. Once your key is in, the first click from your published site makes your own public review page on Formgong, where clients read and leave reviews, and every later click opens it. Switch the page off in Formgong (Reviews → your site → Settings) or change those links.

## Українська

Яскравий односторінковий сайт для практики превентивної або функціональної медицини: один `index.html` і папка `img/`. Практика Tamsa Health, команда, відгуки, ціни й адреса вигадані, це зразковий вміст.

На сторінці:

- шапка-«пігулка», яка над першим екраном прозора, під час прокрутки стає білою, ховається, коли гортаєте вниз, і повертається, коли вгору; на телефоні — кнопка меню і панель запису внизу екрана;
- темний перший екран: три фото змінюються з повільним наближенням, заголовок з'являється слово за словом, три числа праворуч рахуються; наступний блок наїжджає на перший екран;
- «З чого почати»: безкоштовний вступний дзвінок і невеликий підбір — оберіть мету, і сайт підкаже, з чого почати; кнопка «Book this» обирає цю послугу у формі;
- п'ять карток послуг: довгий огляд із прикладом підсумку аналізів, лабораторні панелі, харчування, коучинг, сон і стрес;
- темний блок, де під час прокрутки по черзі змінюються чотири короткі твердження;
- як проходить візит: чотири кроки, лінія заповнюється під час прокрутки;
- команда з чотирьох людей;
- три плани членства з перемикачем «щомісяця / щороку»;
- відгуки з рейтингом і стрілками;
- питання й відповіді;
- темний блок із формою запису;
- футер з адресою, годинами роботи, телефоном і поштою.

Без JavaScript усе видно. З `prefers-reduced-motion: reduce` нічого не рухається.

**Налаштування форми**

1. Створіть форму в кабінеті Formgong і скопіюйте ключ доступу.
2. У `index.html` замініть `fk_your_access_key` на свій ключ.
3. Форма надсилає `name`, `email`, `phone`, `service`, `preferred_time`, `message`, приховане `subject`, а також `access_key` і порожнє поле-пастку `botcheck`. Обов'язкові `name` та `email`; телефон, зручний час і примітка — за бажанням.
4. Подяка з'являється лише тоді, коли Formgong відповідає `success: true`. В іншому разі форма показує помилку і зберігає введене.

**Редагування**

- Кольори на початку стилів: `--ink` (темні блоки й текст), `--cobalt` (сині акценти й картки), `--tang` (мандариновий, кнопки й акценти), `--sky` (світле тло). Шрифти — Fraunces і Figtree.
- Варіанти підбору — радіокнопки в `#goals`: `data-title`, `data-text` і `data-service`.
- Твердження — пункти `<li>` у `.statements`; довжину прокрутки задає `.seq { height: 380vh }`.
- Ціни планів — `data-m` (щомісяця) і `data-y` (щороку). Числа на першому екрані — `data-count`.
- Замініть фото в `img/`, зберігши назви файлів. Промпти — у `img-prompts.json`.

**Зображення.** Дванадцять фото згенеровано для цього шаблону в ChatGPT (OpenAI) і збережено у WebP. Люди й місця вигадані. Їх можна використовувати, але перед запуском замініть їх фото своєї практики й команди.

**Медичні дані.** Ця форма — лише для запитів на запис. Не збирайте через неї діагнози, історію хвороб, рецепти чи номери страхових полісів; зберігайте їх у власній системі пацієнтів клініки. Біля поля примітки є підказка: «Please don't include medical details here — we'll talk about them in person.»

**Зразковий вміст.** Команда, відгуки, рейтинги, ціни, числа, адреса й телефон — приклади. Замініть їх своїми і не публікуйте відгуків, яких ви не отримували.

MIT license.

Посилання «Powered by Formgong» ведуть на `https://formgong.com/review-page/fk_your_access_key`, тож та сама заміна ключа оновить і їх. Коли ключ стоїть, перший перехід з вашого опублікованого сайту створює вашу публічну сторінку відгуків на Formgong, де клієнти читають і залишають відгуки; далі посилання відкриває її. Вимкнути сторінку можна у Formgong (Відгуки → ваш сайт → Налаштування) або змінити ці посилання.
