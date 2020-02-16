### Когда надо выносить переменную

#### Когда выражение слишком сложно и его хочется разбить на части

TODO: пример

#### Когда подвыражение требует комментария

TODO: подобрать пример порепрезентативней.

```
const user = {
  # Здесь сходу непонятно, что значит второй аргумент:
  password_digest: bcrypt.hashSync(password, bcrypt.genSaltSync(SALT_ROUNDS)),
  email: data,
}
```

Вот так не будет вопросов (иллюстрация принципа "код сам себя комментирует"):

```
const salt = bcrypt.genSaltSync(SALT_ROUNDS);
const user = {
  password_digest: bcrypt.hashSync(password, salt),
  email: data,
};
```
