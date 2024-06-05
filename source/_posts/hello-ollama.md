---
title: hello-ollama
date: 2024-06-05 16:54:50
tags: ollama
categories: ollama
---
## Mac上使用Ollama和AnythingLLM部署Llama3模型

### 安装步骤

#### 1. 安装Ollama

- **访问Ollama官网**: https://ollama.com/ 注册并下载适用于macOS的安装包。
- **安装Ollama**: 双击下载的安装包并按照提示完成安装。
- **验证安装**: 在终端中运行以下命令，确保Ollama安装成功：
  ```bash
  ollama
  ```

#### 2. 下载和运行Llama 3模型
- **运行模型**: 使用以下命令启动Llama 3模型：
  ```bash
  ollama run llama3
  ```
  如果本地没有Llama 3模型，Ollama会自动下载模型。

#### 3. 配置AnythingLLM

  AngthingLLM官网：https://useanything.com
  同样的选择对应的系统版本即可
  在配置里配 LLM Preference，LLM provider选择ollama，URL填写默认地址，后面的模型选择llama3，token填4096


#### 4. 测试部署
- **验证运行状态**: 通过浏览器访问`http://127.0.0.1:11434`。


### 常用Ollama命令
- **serve**: 启动Ollama
  ```bash
  ollama serve
  ```
- **create**: 从Modelfile创建模型
  ```bash
  ollama create <model_name>
  ```
- **show**: 显示模型信息
  ```bash
  ollama show <model_name>
  ```
- **run**: 运行模型
  ```bash
  ollama run <model_name>
  ```
- **pull**: 从注册表拉取模型
  ```bash
  ollama pull <model_name>
  ```
- **push**: 将模型推送到注册表
  ```bash
  ollama push <model_name>
  ```
- **list**: 列出所有模型
  ```bash
  ollama list models
  ```
- **cp**: 复制模型
  ```bash
  ollama cp <source_model> <destination_model>
  ```
- **rm**: 删除模型
  ```bash
  ollama rm <model_name>
  ```
- **help**: 获取命令帮助
  ```bash
  ollama help <command>
  ```