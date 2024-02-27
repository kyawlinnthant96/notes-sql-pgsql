## SQL-PGSQL NOTES


### Join Statement
table တွေကို join မလုပ်ခင်မှာ ကိုလိုတဲ့ data table ကိုအရင် order လုပ်ပြီးမှ **left, right or full** သုံးမလားဆိုတာကို စဥ◌်စားလို့ရမှာဖြစ်ပါတယ်. 

join ရဲ့လုပ်ဆောင်ချက်ကတော့ မတူညီတဲ့ table တွေက rows တွေကို ပေါင်းပြီးတော့ data collection table အသစ်တခုကိုတည်ဆောက်ပေးခြင်ကို လုပ်ဆောင်ပေးပါတယ်.ဥပမာ - data ရှာတဲ့ case တခုမှာ user အတွက် table ကတခု comments တွက် table ကတခု total နှစ်ခုဆောက်လိုက်မယ်ပေါ့.

**User Table**

| id | username | 
|----|----------|
| 1  | mgmg     |
| 2  | kyawkyaw |

**Comments Table**

| id | contents    | user_id | photo_id |
|----|-------------|---------|----------|
| 1  | hello world | 1       | 2        |
| 2  | kyawkyaw    | 2       | 1        |

အပေါက table နှစ်ခုကိုသုံးပြီး user comment လုပ်ထားတဲ့ data ကို ဆွဲထုတ်မယ် အောက်က query နဲ့

```
SELECT contents, username FROM comments JOIN users ON users.id = comments.id
```
query ကိုရှင်းရရင် contents နဲ့ username ကို ယူမယ် comments ကို users table နဲ့ join ပြီး user table က id နဲ့ comments table က user_idနဲ့ တူတဲ့ result တွေကိုဆွဲထုတ် ပေးပါဆိုတဲ့ သဘောမျိုးပေါ့.
query မှာ ကျတော်တို့လိုခြင်တဲ့ column ကို select လုပ်ပြီးဆွဲထုတ်ထားတယ်.အောက်က table တိုင်း result ရလာမယ်ပေါ့ 

| contents    | username | 
|-------------|----------|
| hello world | mgmg     | 
| kyawkyaw    | kyawkyaw | 

ဒါကတော့ အခြေခံ table join statement သုံနည်းလေပေါ့.


