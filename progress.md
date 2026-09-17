# 阶段 0：环境与工具 —— 已完成 ✅

完成日期：2026-09-17
实际投入：约 8 小时（7 次课）
教材：DE_stage0_textbook.pdf

---

## 一、学完的内容

### Lesson 0.1　command line
working directory 概念、绝对/相对路径、十个核心指令、flag 结构、
`>` vs `>>`、路径空格与引号、Tab 补全、五种常见错误讯息

### Lesson 0.2　Git 本机
三区模型（书桌→纸箱→仓库）、档案四种状态、`git init` 与 `.git`、
日常工作循环、读 unified diff（hunk header）、commit message 规范、
为什么 `git add` 一个已删除的档案是合理的

### Lesson 0.3　GitHub
Git ≠ GitHub、SSH key 公钥私钥原理、`ssh-keygen` / `ssh-add` / `ssh -T`、
`git remote add` / `set-url`、`git push -u` vs `git push`、
`git branch -M main`、Markdown 语法、README 写法

### Lesson 0.4　branch 与协作
branch 的本质是「指向 commit 的标签」（main 也是）、HEAD 的意义、
`git switch -c` / `switch` / `merge` / `branch -d`、
fast-forward vs three-way merge、merge conflict 四步解法

### Lesson 0.5　.gitignore 与敏感资料
`.gitignore` 六种语法、`!` 例外规则、
**核心限制：只对 untracked 档案有效**、`git rm --cached`、
commit 历史永远捞得回来（`git show <hash>:<file>`）、
外洩处理顺序：revoke → 防呆 → 清历史 → 通报

### Lesson 0.6　VS Code
内建终端设成 Git Bash、`code .`、Source Control 介面、
快捷键、`.py` vs notebook 的取舍

### 补课　restore 与 Pull Request
`git restore` vs `git restore --staged` 的差别（后者安全，前者不可逆）、
PR 七步流程、实际跑过一次 PR（#1 已 merge）

---

## 二、成果

- GitHub repo：github.com/YuJing11/de-learning（Public，13+ commits）
- README 改写三版，从日记语气改成专案说明
- 完整跑过一次 Pull Request 流程并合并
- SSH key 设定完成，`ssh -T` 通过

---

## 三、踩过的坑（不要再犯）

| 坑 | 教训 |
|---|---|
| 专案建在 OneDrive | Git 和同步软件会打架，放 `C:\dev\` |
| `.git` 建在 `/c/dev` 而非专案内 | Git 会往上层找 `.git`；用 `git rev-parse --show-toplevel` 确认 |
| 没有 initial commit 就开分支 | 分支要贴在 commit 上，没快照就没便利贴 |
| `Yujing11` vs `YuJing11` | **Git 区分大小写** |
| `git commit -am` 失败没发现 → 假的合并 | 指令跑完要读输出再走下一步 |
| `echo >>` 让 `.gitignore` 黏成一行 | `>>` 是「接在最尾巴」；档案结尾要留换行 |
| `cat` 了但没读内容 | 输出印出来是要看的 |
| 代码没跑就 commit（`print(Hello)` 缺引号） | 先跑再 commit，两秒挡掉一类错误 |
| 行尾多空白污染 diff | VS Code 开 trim trailing whitespace + insert final newline |

---

## 四、建立起来的三个习惯

1. **指令跑完读输出** —— 两次卡关都是没读输出造成的
2. **卡住的诊断顺序** —— `pwd` → `ls` → `git status` → `git diff`，
   八成问题在前两步找到
3. **先跑再 commit**

---

## 五、下次从这里开始

**阶段 1：SQL**（估算 40–50 小时，约 7–8 周）
教材：DE_learning_roadmap.pdf 第 9–11 页

**第一课要做的事：** 装本机练习资料库 + 生一份假 HR 数据

**⚠️ 提醒自己：** DAX 算的是「某个筛选情境下的值」，
SQL 算的是「把表变成另一个表」。不要用 DAX 直觉套 SQL。

**高优先章节（面试 ★★★）：**
1.3 JOIN 全家（一对多造成的列数膨胀）
1.5 Window function ← 最高频面试题
1.7 SQL 执行顺序

---

## 六、还没做的小事

- [ ] GitHub repo 的 About 描述还是空的
- [ ] VS Code 设定 trim trailing whitespace / insert final newline
- [ ] 下次写 PR 时练习 description（What / Why / 取舍）
