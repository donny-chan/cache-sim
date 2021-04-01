# 实验一：Cache Analysis

DDL：2021.4.3 00:00
清华大学，《计算机系统结构》（张广艳）的课程实验一。
计 82    陈英发    2018080073

使用

## 环境

操作系统：Ubuntu 20.04
编程语言：C++11
实验平台：Lenovo y7000，WSL Ubuntu 20.04。

> 注：请使用 Linux 执行。

## 执行

- 运行所有不同的 cache 组织和策略：`make all`

- 运行不同的 cache 组织：`make structure`

- 运行不同的替换策略：`make replace`

- 运行不同的写策略：`make write`

- 单独运行某一种参数：

  ```bash
  make build
  cd src && ./main <块大小> <组数> <替换策略> <写策略>
  ```

为了方便，代码中块大小（`block_size`）等于 0 代表全相连。

> 注：全相连非常慢，尤其是块大小比较小或者命中率比较低的时候，可能要一个小时以上。如果不想测试全相连，可以在测试文件（`run_structure.sh`）中注释掉。

## 文件结构

- **input**：存放 trace 文件
- **output**：存放模拟结果，包括每一个**重点 trace 的访问 Log**。另外每此用不同参数进行模拟，都会输出一个以参数命名的文件，其中含有一些统计数据。命名格式为：`<块大小>_<块大小>_<块大小>_<块大小>_<块大小>.tsv` 。
- **report**：实验报告
- **src**：源代码