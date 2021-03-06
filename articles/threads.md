## Threads

![Image of Abstraction](https://raw.githubusercontent.com/HlaingTinHtun/Operating-System-For-Programmers/master/images/thread.png)

အရင် article မှာတုန်းကတော့ process အကြောင်းကိုရေးသွားခဲ့ပါတယ်။ အဲ့ဒီ process ကနေပြီးတစ်ဆင့် execution ဖြစ်လာတဲ့ အရာတွေကို thread လို့ခေါ်ပါတယ်။ thread တိုင်းမှာ execute လုပ်ဖို့အတွက် program counter နဲ့ registers တွေပါဝင်ပါတယ်။ program counter , registers တွေအကြောင်းကို မသိသေးရင်တော့ processes ဆိုတဲ့ article ကိုအရင်သွားဖတ်သင့်ပါတယ်။

Process ထဲမှာရှိတဲ့ thread တွေက singly (တစ်ကြိမ်မှာ thread တစ်ခု) လည်း run လို့ရသလို multi-threaded (တစ်ကြိမ်တည်းမှာ thread တစ်ခုထက်မက) လည်း run လို့ရပါတယ်။
process တွေနဲ့ မတူတာက thread တွေက သူတို့အချင်းချင်းကို segment တွေ sharing လုပ်ထားလို့ရပါတယ်။ thread တစ်ခု က တစ်ခုခု change လုပ်လိုက်ပြီဆို တစ်ခြား thread တွေကို သိနိုင်ပါတယ်။ parallel architecture နဲ့ တစ်ပြိုင်နက်ထဲမှာတင် တစ်ခုထက်မက run နိုင်တဲ့ အတွက် light weight ဖြစ်ပြီးတော့ OS ရဲ့ performance ကို improve ဖြစ်စေပါတယ်။

Process နဲ့ thread ကမတူပေမဲ့လည်း relation ရှိပါတယ်။ ကျနော်နားလည်ထားသလောက်ပြောရရင် process ဆိုတာက execution instance တစ်ခုအနေနဲ့ရှိတယ်။ thread တွေက အဲ့ဒီ execution instance ထဲက tasks တွေကို ဆောင်ရွက်ပေးမယ့် actual workers တွေဖြစ်ပါတယ်။ thread ကို real world example တစ်ခုပေးရရင် ကိုယ်က စာအုပ်တစ်အုပ်ဖတ်နေတယ်၊ ခနနားပြီး နောက်မှပြန်ဖတ်ချင်တယ်။ အခုဖတ်တဲ့နေရာကနေ ပြန်ဖတ်ချင်တယ်ဆို စာရွက် number, line number ကိုမှတ်ထားရပါမယ်။ (အဲ့လို process ကို thread ရဲ့ execution context လို့ခေါ်တယ်။ လက်ရှိမှာဆိုရင်တော့ execution context ထဲမှာ number နှစ်ခုပါပါတယ်၊ စာရွက် number ရယ် line number ရယ်)။ တစ်ချိန်ထဲမှာပဲ ကိုယ့်သူငယ်ချင်းတစ်ယောက်ကလဲ စာအုပ်ကိုယူဖတ်ပါတယ်။ သူဆီမှာလည်း ကျနော်လိုပဲ နားပြီးမှပြန်ဖတ်နိုင်ဖို့အတွက် execution context တွေရှိပါတယ်။ thread ရဲ့ အလုပ်လုပ်ပုံကလည်း ဒီပုံစံပဲ၊ computation တစ်ခုဆီတိုင်းမှာ execution context ရှိမယ်၊၊ စာအုပ်ကို ကျနော့်သူငယ်ချင်းနဲ့ share လုပ်ပြီး ဖတ်နိုင်သလို tasks တွေအများကြီးကလည်း CPU ကို share လုပ်ပြီး consume လုပ်နိုင်ပါတယ်။

Process နဲ့ thread ရဲ့ အဓိက ခြားနားချက်က process က computation လုပ်ဖို့အတွက်လိုတဲ့ resource တွေပါတယ်။ thread ကတော့ execution context ပဲဖြစ်တယ်။

user level threads နဲ့ kernel level threads ဆိုပြီး Thread type ၂ မျိုးရှိတယ်။

user level မှာဖြစ်နေတဲ့ threads တွေကိုတော့ kernel က recognize မဖြစ်ဘူး၊ အဲ့ဒီ thread library မှာ thread တွေကို create/delete/schedule အစရှိတာတွေ လုပ်မယ့် code တွေပါတယ်၊ kernel level thread ထက်စာရင် user level thread တွေကပိုမြန်ပြီးတော့ OS မရွေးဘဲ run လို့ရပေမယ့်လို့ တစ်ချို့ OS တွေမှာ block ဖြစ်နိုင်တဲ့ case တွေရှိတယ်၊ ပြီးတော့ multi-processing မရပါဘူး။

Kernel level threads တွေကို OS က တိုက်ရိုက် support လုပ်ပေးထားပါတယ်။ threads တွေ management လုပ်ဖို့ကလဲ kernel ထဲမှာပဲရှိပါတယ်၊ user level application area မှာမရှိပါဘူး။ application တစ်ခုအတွက် process တစ်ခု ၊ အဲ့ process ထဲမှာပဲ threads တွေဖန်တီးပါတယ်။ process ထဲမှာရှိတဲ့ thread တစ်ခုခု block ဖြစ်သွားရင် အလားတူ thread နောက်တစ်ခုကို schedule ပြန်လုပ်ပေးနိုင်တယ်။ multi process architecture ကိုကောင်းကောင်းအလုပ်လုပ်နိုင်တယ်။ process တစ်ခုထဲမှာရှိတဲ့ thread တစ်ခုကနေ တစ်ခုကို control transfer လုပ်ရတဲ့ နေရာမှာတဲ့  Kernel ရဲ့  mode တစ်ခုကို လာပြီးတော့ switch လုပ်ပေးဖို့လိုအပ်ပါတယ်။
