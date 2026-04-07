# 小智 ESP32 固件 (xuqi1987 版本)

基于 [78/xiaozhi-esp32](https://github.com/78/xiaozhi-esp32) 项目，针对 **立创·实战派 ESP32-S3 开发板** 定制。

## 硬件配置

| 项目 | 配置 |
|------|------|
| **开发板** | 立创·实战派 ESP32-S3 |
| **芯片** | ESP32-S3 (QFN56) |
| **Flash** | 16MB |
| **PSRAM** | 8MB |
| **摄像头** | GC0308 |
| **屏幕** | ST7789 240x320 IPS |
| **音频Codec** | ES8311 + ES7210 |
| **触控** | FT5x06 |

## 编译刷写

### 环境要求
- ESP-IDF v5.5.2
- Python 3.10+
- Ubuntu 22.04 (或类似Linux)

### 编译命令

```bash
# 进入项目目录
cd /home/xuqi/xiaozhi

# 加载ESP-IDF环境
source /home/xuqi/esp/v5.5.2/export.sh

# 设置目标芯片
idf.py set-target esp32s3

# 编译并刷写
idf.py -p /dev/ttyUSB0 build flash

# 查看串口日志
idf.py -p /dev/ttyUSB0 monitor
```

### 串口设备
- USB-UART: `/dev/ttyUSB0` (CH340/FTDI)
- 原生USB: `/dev/ttyACM0` (需要 chmod 666)

## 项目结构

```
xiaozhi/
├── main/
│   ├── boards/
│   │   └── lichuang-dev/     # 立创实战派板子适配
│   ├── audio/                # 音频处理 (Opus编解码)
│   ├── display/              # LVGL + ST7789屏幕
│   ├── protocols/           # WebSocket/MQTT协议
│   └── application.cc       # 主应用逻辑
├── build/                    # 编译产物
└── sdkconfig               # ESP-IDF配置
```

## 数据链路

### 声音链路
```
麦克风 → I2S → 音频处理(VAD/AEC) → Opus编码 → WebSocket → 服务器
服务器 → WebSocket → Opus解码 → I2S → 扬声器
```

### 视频链路
```
GC0308摄像头 → RGB565 → JPEG编码 → 本地LCD显示 / 上传服务器
```

## 主要特性

- 离线语音唤醒 (ESP-SR)
- 流式 ASR → LLM → TTS 架构
- 双协议支持 (WebSocket / MQTT+UDP)
- OPUS 音频编解码
- 声纹识别 (3D Speaker)
- MCP 协议扩展
- 多语言支持 (中文/英文/日语)

## 仓库地址

- 主仓库: https://github.com/xuqi1987/xiaozhi-esp32
- 原项目: https://github.com/78/xiaozhi-esp32

## License

继承原项目 MIT License
