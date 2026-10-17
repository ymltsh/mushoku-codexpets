# mushoku-codexpets-doc
请将以下合集中的六只 Pet 导入当前账号宠物库。

## 下载源

- 主源：https://wgen.top/d/Share/0_file/mushoku-six-pets-collection.zip
- 备用：https://ymltsh.lanzoub.com/iE2JS4cav8cd ，密码：`gnyi`

## 执行步骤

1. 下载并解压 ZIP。应得到六个角色文件夹，每个包含 `pet.json` 和 `spritesheet.webp`。
2. 使用 Pets 插件读取当前账号的完整宠物列表，检查是否已安装，避免重复创建；名称相同但无法确认身份时，不要直接覆盖。
3. 读取各文件夹的 `pet.json`，使用 `displayName` 和 `description` 作为名称、描述，保留原始图集。
4. 对每只尚未安装的 Pet，依次调用：
   - `validate_pet_spritesheet(file=图集绝对路径)`，确认 `valid=true`。
   - `prepare_pet_upload(file=同一图集绝对路径)`。
   - `create_pet(name=名称, description=描述, upload_session_id=返回的 upload.upload_session_id)`。
5. 重新读取完整宠物列表，确认六只均存在，报告成功和失败项。默认不切换当前宠物。

## 预期六只

| 文件夹 | 名称 |
|---|---|
| mushoku-roxy-pixel | Roxy Pixel |
| mushoku-sylphie-pixel | Sylphiette Pixel |
| mushoku-eris-pixel | Eris Pixel |
| mushoku-rudeus-pixel | Rudeus Pixel |
| mushoku-roxy-dress-pixel | Roxy Dress Pixel |
| mushoku-sylphie-dress-pixel | Sylphiette Dress Pixel |

无需 npx。仅复制到 `~/.codex/pets/` 不算完成账号宠物库导入。若缺少 Pets 工具、文件访问能力，或校验失败，请说明具体阻碍，不要声称安装成功，不要自行重绘或修改原图。

