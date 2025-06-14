# 自动化行为

自动化集成具有控制自动化的操作，例如打开和关闭自动化。可以在一个自动化中禁用另一个自动化，这将很有用。



## 开启行为 ` automation.turn_on`

此操作将启用自动化的触发器。

| 数据字段    | 是否可选 | 说明                                                         |
| ----------- | -------- | ------------------------------------------------------------ |
| `entity_id` | 必选     | 要操作的自动化的实体 ID。可以是单个，也可以是一个列表。也接受 `none`（无）或 `all`（全部）。 |



## 关闭行为 `automation.turn_off`

| 数据字段（Data attribute）                                   | 是否可选（Optional） | 说明（Description）                                          |
| ------------------------------------------------------------ | -------------------- | ------------------------------------------------------------ |
| `entity_id`                                                  | 必选                 | 要关闭的自动化的实体 ID。可以是一个，也可以是多个（列表形式）。还可以使用 `none` 或 `all`。 |
| `stop_actions | 可选| 是否停止该自动化当前正在执行的动作（默认为 `true`，即会停止）。 |                      |                                                              |



## 转换行为 `automation.toggle`

切换自动化执行的状态，开变成关，关变成开。切换为关的时候直接终止触发器行为。

| 数据字段（Data attribute） | 可选 | 说明                                                         |
| -------------------------- | ---- | ------------------------------------------------------------ |
| `entity_id`                | 必须 | 要切换的自动化的实体 ID，可以是一个，也可以是多个（列表）。也支持 `none` 或 `all`。 |



## 触发行为 `automation.trigger`

这个动作将触发自动化的动作。默认情况下，它会绕过任何条件（通过所有的自动化条件），且默认行为通过 skip_condition 属性进行修改。

| 字段名（Data attribute） | 是否可选 | 中文解释                                                     |
| ------------------------ | -------- | ------------------------------------------------------------ |
| `entity_id`              | 必选     | 要触发的自动化实体 ID。可以是一个 ID，也可以是一个列表。也支持 `none` 或 `all`。 |
| `skip_condition`         | 可选     | 是否跳过 `condition` 条件判断（默认为 `true`，即**跳过**条件判断，直接执行动作）。 |



## 重新加载行为`automation.reload`

仅当您在 YAML 中创建 / 编辑自动化时，才需要执行此操作。通过 UI 的自动化会自动执行此操作。

此操作重新加载所有自动化，停止所有当前活跃的自动化操作。



