# Новый Адвент для Василисы · 2026

Публичная страница: `/advent-vasilisa-2026/`  
Мамин кабинет: `/advent-vasilisa-2026/admin.html`

## Подключение Supabase
1. Создать Supabase project.
2. В SQL Editor выполнить `supabase/schema.sql`.
3. В Authentication создать пользователя-администратора с email и паролем.
4. В SQL Editor добавить его UUID в `public.advent_admins`:
   `insert into public.advent_admins(user_id) values ('UUID_ПОЛЬЗОВАТЕЛЯ');`
5. В `config.js` указать Project URL и publishable/anon key из Supabase Project Settings → API.
6. После этого войти в `admin.html`, выбрать день и добавлять письма, задания, фотографии, видео и аудио.

Файлы медиа сохраняются в Supabase Storage (bucket `advent-media`). Тексты и ссылки — в таблице `advent_days`. Ответы Василисы — в `child_messages`.

## Важно
- В браузере используется только публичный publishable/anon key. Никогда не помещать secret/service_role key в GitHub или клиентский код.
- Таблицы защищены RLS. Для доступа к редактору UUID пользователя должен быть внесён в `advent_admins`.
- GitHub Pages обслуживает статические файлы, а Supabase хранит редактируемое содержимое.
