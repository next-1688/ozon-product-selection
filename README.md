# ozon-product-selection

Ozon电商选品工具：根据品类自动搜索热门细分市场，从1688找到最优货源。

## 功能

- 根据品类搜索Ozon市场趋势
- AI提取5-8个热门细分关键词
- 调用1688搜索API查找商品（最多输出3个）
- 按价格、起批量、发货率、销量筛选
- 输出SKU明细及建议售价

## 环境要求

Python 3.x

## 安装

```bash
pip install -r requirements.txt
```

## 配置

需要配置以下环境变量：

```bash
export ALPHASHOP_ACCESS_KEY="your_access_key"
export ALPHASHOP_SECRET_KEY="your_secret_key"
```

获取密钥：https://www.alphashop.cn/seller-center/apikey-management

## 使用

```bash
python3 scripts/search_products.py "关键词" [选项]
```

### 选项

- `--max-price` - 最高单价（元）
- `--max-moq` - 最大起批量（件）
- `--min-ship-rate-48h` - 最低48H发货率（%）
- `--min-sales` - 最低年销量（件）
- `--top` - 返回结果数量（默认3）

### 示例

```bash
python3 scripts/search_products.py "儿童玩具" --max-price 50 --max-moq 10 --min-ship-rate-48h 80
```

## 输出格式

返回JSON格式，包含商品信息、SKU明细、供应商信息等。
