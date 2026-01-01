# 更新仓库步骤说明 | Repository Update Steps

由于项目结构完全重构，需要清空远程仓库并重新上传新结构。

Since the project structure is completely restructured, we need to clear the remote repository and re-upload the new structure.

## 方案一：强制推送（推荐，如果只有你一个人使用这个仓库）
## Option 1: Force Push (Recommended if you're the only one using this repo)

```bash
# 1. 添加所有更改（包括删除和新文件）
git add -A

# 2. 提交更改
git commit -m "Complete project restructure: update structure and add new directories"

# 3. 强制推送到远程（会覆盖远程仓库）
git push origin main --force
```

**警告**: `--force` 会覆盖远程仓库的历史记录，如果其他人也在使用这个仓库，不要用这个方法。

**Warning**: `--force` will overwrite the remote repository history. Don't use this if others are using the repo.

---

## 方案二：安全方式（保留历史记录）
## Option 2: Safe Approach (Preserves history)

```bash
# 1. 先拉取远程更改（如果需要合并）
git pull origin main

# 2. 添加所有更改
git add -A

# 3. 提交更改
git commit -m "Complete project restructure: update structure and add new directories"

# 4. 推送到远程
git push origin main
```

---

## 要上传的文件夹/文件
## Folders/Files to Upload

根据您的要求，以下内容会被上传：
According to your requirements, the following will be uploaded:

- ✅ `dataset/`
- ✅ `docs/`
- ✅ `examples/`
- ✅ `resources/`
- ✅ `scripts/`
- ✅ `README.md`
- ✅ `.gitignore` (已更新，忽略简历文件)

以下文件会被忽略（已在.gitignore中）：
The following files will be ignored (already in .gitignore):

- ❌ `*简历*.tex`
- ❌ `*项目经历*.tex`
- ❌ `技能描述.tex`

## 注意事项
## Notes

1. 确保 `.gitignore` 已正确配置（已完成 ✅）
2. Make sure `.gitignore` is properly configured (Done ✅)
3. 提交前可以运行 `git status` 检查哪些文件会被提交
4. You can run `git status` before committing to check which files will be committed
5. 如果远程仓库有重要内容，建议先备份
6. If the remote repository has important content, consider backing it up first

