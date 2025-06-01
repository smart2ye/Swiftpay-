إليك نسخة كاملة من المشروع على شكل ملف HTML مستقل يعمل كمساعد ذكي بسيط باللغة العربية (اللهجة اليمنية). هذا الملف لا يعتمد على خادم خارجي، ويحتوي على منطق الردود مباشرة باستخدام JavaScript:

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <title>🧠 مساعد مزلي الذكي</title>
  <style>
    body {
      font-family: 'Cairo', sans-serif;
      background-color: #f8f8f8;
      padding: 2rem;
      text-align: center;
    }
    input, button {
      padding: 10px;
      font-size: 1rem;
      margin: 10px;
    }
    #response {
      margin-top: 20px;
      font-weight: bold;
      font-size: 1.2rem;
      color: #444;
    }
  </style>
</head>
<body>
  <h2>🧠 مساعد مزلي المالي - نسخة بدون إنترنت</h2>
  <p>اسأل: <em>كم صرفت على سبأفون؟</em> أو <em>ذكّرني بدفع يمن نت</em></p>
  <input type="text" id="query" placeholder="أدخل استفسارك هنا" size="50">
  <button onclick="respond()">أرسل</button>
  <div id="response"></div>

  <script>
    const expenses = [
      { amount: 2000, category: "سبأفون" },
      { amount: 500, category: "يمن نت" },
      { amount: 3500, category: "سبأفون" },
      { amount: 1200, category: "MTN" },
      { amount: 1000, category: "سبأفون" },
    ];

    function respond() {
      const input = document.getElementById("query").value.toLowerCase();
      let response = "🔍 لم أفهم سؤالك، حاول مرة أخرى.";

      if (input.includes("سبأفون") && (input.includes("كم") || input.includes("قد صرفت"))) {
        const total = expenses.filter(e => e.category === "سبأفون")
                              .reduce((sum, e) => sum + e.amount, 0);
        response = `صرفك الكلي على سبأفون هو ${total.toLocaleString()} ريال.`;
      } else if (input.includes("يمن نت")) {
        const total = expenses.filter(e => e.category === "يمن نت")
                              .reduce((sum, e) => sum + e.amount, 0);
        response = `صرفك على يمن نت هو ${total.toLocaleString()} ريال.`;
      } else if (input.includes("ذكّرني")) {
        response = "✅ تم إضافة التذكير (تجريبي فقط).";
      }

      document.getElementById("response").innerText = response;
    }
  </script>
</body>
</html>

✅ المميزات:

يعمل بدون خادم أو اتصال إنترنت.

يحلل استعلامات باللهجة اليمنية مثل: "كم صرفت على سبأفون؟"

يحاكي منطق الذكاء الاصطناعي بطريقة مبسطة



---

هل ترغب أن أجهز لك نسخة .apk من هذا المساعد أيضًا باستخدام WebView؟

