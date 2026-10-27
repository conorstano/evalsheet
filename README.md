# evalsheet

**把一组评测结果汇成带置信区间的分数卡。**

`evalsheet` —— 把多维评测结果整理成分数卡，给出每维的样本量、均值与置信区间

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`evalsheet.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install conorstano-evalsheet
```

装完直接用命令名调用：

```bash
evalsheet --help
```

也可以不用安装，直接把 `evalsheet.py` 拷走用——它只依赖标准库。

## 为什么需要它

每维都标样本量，样本不足的维度会被明确标为不可用

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测分数卡 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python evalsheet.py --file input.txt
python evalsheet.py --text "示例内容"
python evalsheet.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 阈值是固定值，不随数据自适应。
- 只判定达标与否，不解释分数来源。

## 跑测试

```bash
python test_evalsheet.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/conorstano/evalsheet>

---

## 关于作者

conorstano 做评测分数卡相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://conorstano.github.io>
- 仓库：<https://github.com/conorstano/evalsheet>

## 许可

MIT，见 [LICENSE](LICENSE)。
