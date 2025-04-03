# Shiyi-Robocode
A dynamic Robocode robot with radar locking and adaptive movement
## 功能描述
核心功能：
1.动态移动：采用随机转向策略（左转或右转90度），结合长期前进/后退指令（40000像素），形成不可预测的运动轨迹。撞墙或碰撞时自动反弹（reverseDirection）。
2.雷达锁定：雷达独立于机身转动（setAdjustRadarForRobotTurn(true)），通过1.5倍角度修正持续锁定敌人。未发现敌人时持续旋转扫描（setTurnRadarRight(360)）。
3.智能攻击：炮管独立瞄准（setAdjustGunForRobotTurn(true)），根据敌人距离动态调整火力（3-0.1威力）。仅当炮管冷却（getGunHeat() == 0）时开火，避免能量浪费。
4.防御机制：被子弹击中时反向移动并随机转向（90 - e.getBearing()）。与敌人或墙壁碰撞时立即反弹。

## 编译运行
1. 将 'sample/Shiyi.java'复制到 Robocode 的 'robots/sample/' 目录
2. 在 Robocode 中加载机器人
