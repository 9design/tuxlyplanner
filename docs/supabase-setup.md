# Supabase setup

## 1. Project aanmaken

Ga naar [supabase.com](https://supabase.com), maak een gratis account aan en start een nieuw project.

## 2. Tabellen aanmaken

Ga naar de SQL editor in je Supabase dashboard en voer dit uit:

```sql
create table if not exists planner_templates (
  user_id     text not null,
  template_id text not null,
  name        text not null,
  color       text not null default '#2d6cff',
  cards       jsonb not null default '[]',
  updated_at  timestamptz not null default now(),
  primary key (user_id, template_id)
);

create table if not exists planner_days (
  user_id      text not null,
  date         text not null,
  template_id  text not null default 'doordeweeks',
  done         jsonb not null default '[]',
  notebook     text not null default '',
  updated_at   timestamptz not null default now(),
  primary key (user_id, date)
);

alter table planner_templates enable row level security;
alter table planner_days enable row level security;

create policy "open access templates" on planner_templates for all using (true) with check (true);
create policy "open access days"      on planner_days      for all using (true) with check (true);
```

## 3. Keys kopiëren

Ga naar **Project Settings → API** en kopieer:
- **Project URL** → `SB_URL`
- **anon / public key** → `SB_KEY`

## 4. Plakken in index.html

Zoek bovenin het script-blok:

```js
const SB_URL = 'https://jouw-project-id.supabase.co';
const SB_KEY = 'jouw-anon-key-hier';
```

Klaar. Data wordt per gebruiker opgeslagen via een automatisch gegenereerde UUID.
