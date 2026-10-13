# llicotton-images

`llicotton.com` 商品图的本地镜像副本（图片 CDN 失效时的兜底存档）。

## 这是什么

从 `llicotton.com` 的商城商品清单里打包出来的商品图，**文件名是原图 URL 的 MD5**，
扩展名按**文件头魔数**判定（源站 CDN 会按 `Accept` 头做内容协商，
URL 写着 `.png` 回来的可能是 `.webp`，照抄后缀会导致服务器的 `Content-Type` 错配）。

## 目录结构

```
images/<MD5 前 2 位>/<MD5>.<ext>
```

用内容哈希命名 = **URL 天然不可变**，放在任何静态托管上都不会有 CDN 缓存不刷新的问题。

## 用途

仅作备份。Shopify 导入 CSV 时会自行把图转存到 `cdn.shopify.com`，
导入成功后本仓库与线上商品图**不再有任何依赖关系**。

统计：4896 张 / 739.8 MB
