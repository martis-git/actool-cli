## Rules

> Позже будет разбито по файлам в `/docs/rules/{rule}.md`

- `actool/max-tags` - ограничение количества тегов TODO/FIXME в коде
   - `{ todo: number }` - ограничение общего кол-ва TODO меток (default = 16)
   - `{ fixme: number }` - ограничение общего кол-ва FIXME меток (default = 16)
- `actool/live-doclets-block` - добавление обновляемости доклетов, в зависимости от изменения блока кода
  - `{ diff: number }` - приемлемая разница (граница) между кол-вом коммитов доклета и блока кода (с фильтрацией лишних коммитов) (default=4)
   > TODO: Добавить возможность выбирать - по коммитам или дате?
   > - Получаем последний коммит для доклета и кода и вычисляем разницу (=> Commit[])
   > - Убираем лишние коммиты, оставляя только те, что затрагивали код (=> Commit[])
   > - Считаем кол-во оставшихся коммитов (=> number)
- `actool/live-doclets-line` - аналогично `actool/live-doclets-block` (но можно задать свой конфиг)
- `actool/live-doclets-module` - (нужен ли?)
- `actool/no-commented-code` - ограничение использования закомментированного кода
   - `{ when: "always" |  "expired" }` - срабатывание валидатора `всегда`/`по истечению срока` (default="always")
   - `{ diff: number }` - приемлемая разница между кол-вом коммитов "живого" кода и закомментированного
      - Либо по граничным блокам
      - Либо в файле