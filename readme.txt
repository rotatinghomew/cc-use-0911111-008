接种名册流程机器人

该项目模拟接种名册录入与核验流程，把本地业务表单转换为可恢复的机器人会话，记录每一步操作、校验结果和重试状态。演示入口使用 fixtures/demo.json 驱动完整流程，并将会话数据保存到本地 SQLite 数据库。

测试：python3 -m unittest discover -s tests/robot_sessions -p 'test_*.py'
构建：python3 -m compileall -q hpv_roster_robot
验收：python3 -m hpv_roster_robot.runner fixtures/demo.json --db /tmp/hpv_roster_robot-acceptance.sqlite3
