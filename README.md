# rtt-ssd1306
RT-Thread package for working with  OLEDs based on SSD1306, SH1106, SH1107 and SSD1309, supports I2C and SPI. Inspired by stm32-ssd1306.



## 1、介绍

ssd1306 是兼容基于 SSD1306、SH1106、SH1107 和 SSD1309 的 OLED 驱动软件包，支持 I2C 和 SPI 接口。参考 afiskon 的 [stm32-ssd1306](git@github.com:afiskon/stm32-ssd1306.git) 项目进行移植，对接 RT-Thread 操作系统。

目前支持 RT-Thread 软件 I2C 接口，后续将完善对硬件 I2C 和 SPI 的支持。



### 1.1 目录结构

| 名称     | 说明       |
| -------- | ---------- |
| examples | 例子目录   |
| inc      | 头文件目录 |
| src      | 源代码目录 |
| tools    | 工具目录   |



### 1.2 许可证

ssd1306 软件包遵循 MIT 许可，详见 `LICENSE` 文件。



## 2、获取 ssd1306 软件包

使用 ssd1306 package 需要在 RT-Thread 的包管理器中选择它，具体路径如下：

```
RT-Thread online packages --->
    peripheral libraries and drivers --->
        [*] ssd1306: OLEDs based on SSD1306, SH1106, SH1107 and SSD1309 driver  --->
```

然后让 RT-Thread 的包管理器自动更新，或者使用 `pkgs --update` 命令更新包到 BSP 中。



## 3、API 说明

### 初始化

```c
void ssd1306_Init(void);
```

### 填充

```c
void ssd1306_Fill(SSD1306_COLOR color);
```

### 刷新屏幕

```c
void ssd1306_UpdateScreen(void);
```

### 画像素

```c
void ssd1306_DrawPixel(uint8_t x, uint8_t y, SSD1306_COLOR color);
```

### 打印字符

```c
char ssd1306_WriteChar(char ch, FontDef Font, SSD1306_COLOR color);
```

### 打印字符串

```c
char ssd1306_WriteString(char* str, FontDef Font, SSD1306_COLOR color);
```

### 设置光标

```c
void ssd1306_SetCursor(uint8_t x, uint8_t y);
```

### 画直线

```c
void ssd1306_Line(uint8_t x1, uint8_t y1, uint8_t x2, uint8_t y2, SSD1306_COLOR color);
```

### 画弧线

```c
void ssd1306_DrawArc(uint8_t x, uint8_t y, uint8_t radius, uint16_t start_angle, uint16_t sweep, SSD1306_COLOR color);
```

### 画圆

```c
void ssd1306_DrawCircle(uint8_t par_x, uint8_t par_y, uint8_t par_r, SSD1306_COLOR color);
```

### 画折线

```c
void ssd1306_Polyline(const SSD1306_VERTEX *par_vertex, uint16_t par_size, SSD1306_COLOR color);
```

### 画矩形

```c
void ssd1306_DrawRectangle(uint8_t x1, uint8_t y1, uint8_t x2, uint8_t y2, SSD1306_COLOR color);
```



## 4、联系方式

- 维护：luhuadong@163.com
- 主页：<https://github.com/luhuadong/rtt-ssd1306>

