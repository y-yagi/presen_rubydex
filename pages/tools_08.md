---
zoom: 0.85
---

# dead code

* `rdx dead_code`で、どこからも参照されていない定数(クラス・モジュール・定数)の一覧が出せる

```bash
$ bundle exec rdx dead_code
...
Admin
  app/models/admin.rb:1,1-2,4

UsersController
  app/controllers/users_controller.rb:1,1-6,4

3065 files inspected, 3943 dead code candidates found
```

* 対象は定数のみで、メソッドや変数は対象外
  * gemも対象。凄い事になる。
* あくまで候補。メタプログラミングなどで使われているものも含まれるので、削除の際は注意が必要
