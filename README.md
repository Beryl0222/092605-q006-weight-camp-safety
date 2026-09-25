# 减重训练安全干预

本项目提供减重训练安全干预的服务端基础，已有代码包含基础登记对象、可替换时钟、SQLite 本地保存、健康检查、JSON 请求入口和命令行调用。领域模块保持小而清晰，便于继续形成完整业务流程。

## 目录

- `src/weight_camp_safety/domain.py` 保存基础领域对象。
- `src/weight_camp_safety/store.py` 管理 SQLite 表结构和事务写入。
- `src/weight_camp_safety/service.py` 组织登记与查询行为。
- `src/weight_camp_safety/api.py` 提供进程内 JSON 请求边界。
- `tests/` 覆盖当前已有行为。

## 运行

运行测试：`PYTHONPATH=src python3 -m unittest discover -s tests`

检查源码：`python3 -m compileall src`

本地冒烟：`printf '%s' '{"action":"health"}' | PYTHONPATH=src python3 -m weight_camp_safety.cli`

项目只使用 Python 标准库，运行期间不连接其他服务。
