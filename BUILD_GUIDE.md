# 小智 ESP32 固件编译指南

## 环境要求

- Ubuntu 22.04 x86_64
- ESP-IDF v5.5.2
- Python 3.10+
- USB 驱动 (CH340/FTDI 或 ESP32-S3 原生 USB)

## 硬件连接

| 开发板 | 串口 | 备注 |
|--------|------|------|
| 立创实战派 ESP32-S3 |  | 原生 USB |
| 其他 CH340 开发板 |  | USB-UART |

## 一、ESP-IDF 环境配置

### 1. 加载环境


### 2. 验证环境


## 二、编译固件

### 方式一：编译 + 刷写（一步完成）


### 方式二：分步执行

#### 步骤1: 设置目标芯片


#### 步骤2: 配置项目（可选）

常用配置：
-  → 选择板子类型
-  → LCD/摄像头配置

#### 步骤3: 编译


#### 步骤4: 刷写


## 三、查看串口日志



退出 monitor:  或  然后 

## 四、常用命令

| 命令 | 说明 |
|------|------|
|  | 仅编译 |
|  | 仅刷写（不编译）|
|  | 指定串口刷写 |
|  | 查看串口日志 |
|  | 编译+刷写+监控 |
|  | 清理编译产物 |
|  | 重新配置项目 |

## 五、选择板子类型

编译前需确认 sdkconfig 中的板子配置：



常用板子：
-  - 立创实战派 ESP32-S3
-  - 面包板 ESP32-S3 带摄像头

## 六、故障排除

### 刷写失败


### 编译报错


### 串口无法识别
Bus 002 Device 003: ID 0bda:0415 Realtek Semiconductor Corp. USB3.2 Hub
Bus 002 Device 004: ID 0080:a001 Unknown JMS578 based SATA bridge
Bus 002 Device 002: ID 0bda:0411 Realtek Semiconductor Corp. Hub
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
Bus 001 Device 003: ID 0bda:5415 Realtek Semiconductor Corp. USB2.1 Hub
Bus 001 Device 002: ID 0bda:5411 Realtek Semiconductor Corp. RTS5411 Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
/dev/tty
/dev/tty0
/dev/tty1
/dev/tty10
/dev/tty11
/dev/tty12
/dev/tty13
/dev/tty14
/dev/tty15
/dev/tty16
/dev/tty17
/dev/tty18
/dev/tty19
/dev/tty2
/dev/tty20
/dev/tty21
/dev/tty22
/dev/tty23
/dev/tty24
/dev/tty25
/dev/tty26
/dev/tty27
/dev/tty28
/dev/tty29
/dev/tty3
/dev/tty30
/dev/tty31
/dev/tty32
/dev/tty33
/dev/tty34
/dev/tty35
/dev/tty36
/dev/tty37
/dev/tty38
/dev/tty39
/dev/tty4
/dev/tty40
/dev/tty41
/dev/tty42
/dev/tty43
/dev/tty44
/dev/tty45
/dev/tty46
/dev/tty47
/dev/tty48
/dev/tty49
/dev/tty5
/dev/tty50
/dev/tty51
/dev/tty52
/dev/tty53
/dev/tty54
/dev/tty55
/dev/tty56
/dev/tty57
/dev/tty58
/dev/tty59
/dev/tty6
/dev/tty60
/dev/tty61
/dev/tty62
/dev/tty63
/dev/tty7
/dev/tty8
/dev/tty9
/dev/ttyS0
/dev/ttyS1
/dev/ttyS2
/dev/ttyS3

## 七、项目结构



## 八、固件信息

| 项目 | 值 |
|------|-----|
| 芯片 | ESP32-S3 |
| Flash | 16MB |
| 主固件大小 | ~2.9MB |
| 资源分区 | 8MB |
| 编译用户 | xuqi |
| 代码仓库 | https://github.com/xuqi1987/xiaozhi-esp32 |

## 九、一键刷写脚本

创建快捷脚本 :


使用:

