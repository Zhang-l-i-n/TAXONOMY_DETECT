
# TAXONOMY_DETECT
## 项目简介
TAXONOMY_DETECT是一个基于大型语言模型（LLM）的_taxonomy_评估工具。
## 文件夹结构说明
### prompt文件夹
该文件夹包含用于评估的三个不同层级的prompt。每个prompt针对taxonomy中的一个特定层级，用于指导LLM进行评估。
### data文件夹
包含taxonomy示例数据。
#### taxonomy
存放整理好的taxonomy树结构数据。数据应以自上而下的方式组织，便于评估过程中的层级遍历。
## 使用步骤
### Step1: 整理TAXONOMY数据
1. 将TAXONOMY数据整理为自上而下的树结构。
2. 将整理好的数据存放在`data/taxonomy`目录下。
### Step2: 配置评估参数
1. 打开`main/score.py`文件。
2. 根据需要配置以下参数：
   - `span_type`：子树划分的类型。可选值为`dynamic`和`static`。
     - `dynamic`：根据span动态调整子树大小。
     - `static`：子树中的关系数量固定为span。
### Step3: 运行评估脚本
1. 在命令行中运行以下命令：
   ```
   python main/score.py
   ```
2. 脚本将自动生成三个层级的评估prompt，并存放在`result`文件夹中。
