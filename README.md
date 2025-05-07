# Anki MCP 服务器

一个 MCP 服务器实现，连接到本地运行的 Anki，提供卡片复习和创建功能。

该服务器设计用于与 [Anki 桌面应用程序](https://apps.ankiweb.net/) 和 [Anki-Connect](https://foosoft.net/projects/anki-connect/) 插件配合使用。

在使用前，请确保已安装该插件。

## 资源

- **anki://search/deckcurrent**
  - 返回当前牌组中的所有卡片
  - 相当于 Anki 中的 `deck:current`
- **anki://search/isdue**
  - 返回复习和学习中等待学习的卡片
  - 相当于 Anki 中的 `is:due`
- **anki://search/isnew**
  - 返回所有未见过的卡片
  - 相当于 Anki 中的 `is:new`

## 工具

- **update_cards**
  - 将具有给定卡片 ID 的卡片标记为已回答，并为其指定一个从 1 (再次) 到 4 (简单) 的简易度分数
  - 输入:
    - `answers` (数组): 包含 `cardId` (数字) 和 `ease` (数字) 字段的对象数组

- **add_card**
  - 在默认的 Anki 牌组中创建一张新卡片
  - 输入:
    - `front` (字符串): 卡片正面
    - `back` (字符串): 卡片背面

- **get_due_cards**
  - 返回 n 张当前到期应复习的卡片
  - 输入:
    - `num` (数字): 卡片数量

- **get_new_cards**
  - 从新卡片中返回 n 张卡片
  - 输入:
    - `num` (数字): 卡片数量

## 开发

安装依赖:
```bash
npm install
