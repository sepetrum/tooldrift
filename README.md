# tooldrift

**检查工具的实际行为与其描述声明是否一致。**

`tooldrift` —— 比对工具描述与实际调用结果，标出描述与行为不符之处

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`tooldrift.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install sepetrum-tooldrift
```

装完直接用命令名调用：

```bash
tooldrift --help
```

也可以不用安装，直接把 `tooldrift.py` 拷走用——它只依赖标准库。

## 为什么需要它

描述漂移会让智能体持续选错工具，工具从行为侧取证

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 工具描述漂移 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python tooldrift.py --file input.txt
python tooldrift.py --text "示例内容"
python tooldrift.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 一致性靠字面差异判定，语义等价但写法不同会误报。
- 不解析跨文档的引用关系。

## 跑测试

```bash
python test_tooldrift.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/sepetrum/tooldrift>

---

## 关于作者

sepetrum 做工具描述漂移相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://sepetrum.github.io>
- 仓库：<https://github.com/sepetrum/tooldrift>

## 许可

MIT，见 [LICENSE](LICENSE)。
