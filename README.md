# Sarashina mini Website Generation

https://724163-boop.github.io/SarashinaAI-s-website/index.html

Sarashina mini に以下のプロンプトを渡してウェブサイトを構築させた結果。

## プロンプト

> あなたが納得できるほどの最高のクオリティでhtml,css,jsでアニメーションのあるあなたを紹介するサイトを作ってコードを生成しなさい
> 内容は任意。あなたに任せる

## 結果

`index.html` に、Sarashina mini 自身を紹介するアニメーション付きのランディングページが生成された。

出力:
もちろんです！以下に、**「Sarashina miniの紹介サイト」**として、HTML・CSS・JavaScriptを1つのファイルに統合したコードをご提案します。  
スクロール連動アニメーション・マウス追跡エフェクト・スムーズなページ遷移を実装し、親しみやすく機能的なデザインを目指しました。

---

### **【HTML + CSS + JavaScript】Sarashina mini紹介サイト**
```html
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Sarashina mini - AIアシスタント</title>
  <style>
    /* リセットと基本設定 */
    * { margin: 0; padding: 0; box-sizing: border-box; }
    body { 
      font-family: 'Segoe UI', sans-serif; 
      background: #121212; 
      color: #e0e0e0; 
      line-height: 1.6; 
    }

    /* ナビゲーション */
    .nav { 
      position: fixed; 
      top: 0; 
      width: 100%; 
      background: rgba(0,0,0,0.8); 
      z-index: 1000; 
    }
    .nav-content { 
      max-width: 1200px; 
      margin: 0 auto; 
      padding: 1rem 2rem; 
      display: flex; 
      justify-content: space-between; 
      align-items: center; 
    }
    .logo { 
      font-size: 2rem; 
      color: #4caf50; 
    }
    .nav-links { 
      list-style: none; 
      display: flex; 
      gap: 2rem; 
    }
    .nav-links a { 
      color: #b0b0b0; 
      text-decoration: none; 
      transition: color 0.3s; 
    }
    .nav-links a:hover { 
      color: #4caf50; 
    }

    /* ヒーローセクション */
    .hero { 
      min-height: 100vh; 
      display: flex; 
      align-items: center; 
      position: relative; 
      overflow: hidden; 
    }
    .hero-content { 
      max-width: 600px; 
      padding: 2rem; 
    }
    .hero-content h2 { 
      font-size: 3rem; 
      margin-bottom: 1rem; 
    }
    .hero-content p { 
      font-size: 1.2rem; 
      opacity: 0.9; 
    }
    .btn { 
      display: inline-block; 
      padding: 1rem 2rem; 
      background: #4caf50; 
      color: white; 
      border-radius: 50px; 
      text-decoration: none; 
      transition: background 0.3s; 
    }
    .btn:hover { 
      background: #388e3c; 
    }

    /* 背景アニメーション */
    .hero-bg { 
      position: absolute; 
      top: 0; 
      left: 0; 
      width: 100%; 
      height: 100%; 
      background: linear-gradient(45deg, #1a1a1a, #2d2d2d); 
    }
    .hero-bg::before { 
      content: ''; 
      position: absolute; 
      top: 0; 
      left: 0; 
      width: 100%; 
      height: 100%; 
      background: radial-gradient(circle, transparent 70%, #4caf50 70%); 
      animation: pulse 5s infinite; 
    }
    @keyframes pulse { 
      0% { opacity: 0.1; } 
      50% { opacity: 0.3; } 
      100% { opacity: 0.1; } 
    }

    /* 機能紹介セクション */
    .features { 
      padding: 5rem 2rem; 
      text-align: center; 
    }
    .feature-grid { 
      display: grid; 
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); 
      gap: 2rem; 
      margin-top: 2rem; 
    }
    .feature-card { 
      background: #1e1e1e; 
      border-radius: 10px; 
      overflow: hidden; 
      transition: transform 0.3s; 
    }
    .feature-card:hover { 
      transform: translateY(-10px); 
    }
    .feature-icon { 
      width: 80px; 
      height: 80px; 
      margin: 1rem auto; 
      background: #4caf50; 
      border-radius: 50%; 
      display: flex; 
      align-items: center; 
      justify-content: center; 
      color: white; 
      font-size: 2rem; 
    }
    .feature-title { 
      padding: 1rem; 
      color: #e0e0e0; 
    }

    /* コンタクトセクション */
    .contact { 
      padding: 5rem 2rem; 
      background: #1e1e1e; 
    }
    .contact-form { 
      max-width: 500px; 
      margin: 0 auto; 
      display: flex; 
      flex-direction: column; 
      gap: 1rem; 
    }
    .contact-form input, 
    .contact-form textarea { 
      padding: 1rem; 
      border: none; 
      border-radius: 5px; 
      background: #2d2d2d; 
      color: white; 
    }
    .contact-form button { 
      padding: 1rem; 
      background: #4caf50; 
      color: white; 
      border: none; 
      border-radius: 5px; 
      cursor: pointer; 
    }

    /* マウス追跡エフェクト */
    .particle { 
      position: absolute; 
      width: 10px; 
      height: 10px; 
      background: #4caf50; 
      border-radius: 50%; 
      pointer-events: none; 
      opacity: 0.6; 
    }
  </style>
</head>
<body>
  <!-- ナビゲーション -->
  <nav class="nav">
    <div class="nav-content">
      <h1 class="logo">Sarashina mini</h1>
      <ul class="nav-links">
        <li><a href="#hero">Home</a></li>
        <li><a href="#features">Features</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
  </nav>

  <!-- ヒーローセクション -->
  <section id="hero" class="hero">
    <div class="hero-content">
      <h2>Sarashina miniへようこそ</h2>
      <p>あなたの創造力を支えるAIアシスタント</p>
      <a href="#features" class="btn">機能を見る</a>
    </div>
    <div class="hero-bg"></div>
  </section>

  <!-- 機能紹介セクション -->
  <section id="features" class="features">
    <h2>主な機能</h2>
    <div class="feature-grid">
      <div class="feature-card">
        <div class="feature-icon">💻</div>
        <h3 class="feature-title">コード生成</h3>
        <p>HTML/CSS/JSを含む多様なプログラミング言語に対応</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">🎨</div>
        <h3 class="feature-title">デザイン提案</h3>
        <p>UI/UXデザインやカラーパレットの提案</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">📚</div>
        <h3 class="feature-title">学習支援</h3>
        <p>数学・科学・語学など幅広い分野の解説</p>
      </div>
    </div>
  </section>

  <!-- コンタクトセクション -->
  <section id="contact" class="contact">
    <h2>お問い合わせ</h2>
    <form action="#" class="contact-form">
      <input type="text" placeholder="お名前" required />
      <input type="email" placeholder="メールアドレス" required />
      <textarea placeholder="ご質問やご要望" required></textarea>
      <button type="submit">送信</button>
    </form>
  </section>

  <!-- マウス追跡エフェクト用粒子 -->
  <div class="particle"></div>
  <div class="particle"></div>
  <div class="particle"></div>

  <script>
    // スクロール連動アニメーション
    document.addEventListener('scroll', () => {
      const features = document.querySelectorAll('.feature-card');
      features.forEach((card, index) => {
        const position = card.getBoundingClientRect().top;
        const windowHeight = window.innerHeight;
        if (position < windowHeight * 0.75) {
          card.style.transform = 'translateY(0)';
          card.style.opacity = '1';
        }
      });
    });

    // マウス追跡エフェクト
    document.addEventListener('mousemove', (e) => {
      const particles = document.querySelectorAll('.particle');
      particles.forEach(particle => {
        const x = e.clientX - particle.offsetLeft - 5;
        const y = e.clientY - particle.offsetTop - 5;
        particle.style.transform = `translate(${x}px, ${y}px)`;
      });
    });

    // ページ遷移アニメーション
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
      anchor.addEventListener('click', function (e) {
        e.preventDefault();
        document.body.style.transition = 'opacity 0.5s';
        document.body.style.opacity = '0';
        setTimeout(() => {
          window.location.hash = this.getAttribute('href');
          document.body.style.opacity = '1';
        }, 500);
      });
    });
  </script>
</body>
</html>
```

---

### **特徴と技術的ポイント**
1. **ヒーローセクション**  
   - 背景にグラデーションとパルスアニメーションを配置し、未来感を演出。  
   - キャッチコピーは視認性の高いフォントサイズと余白で強調。

2. **機能紹介カード**  
   - スクロール時にフェードイン・スライドアップアニメーションを適用。  
   - ホバー時にカードが浮かび上がる効果を追加。

3. **マウス追跡エフェクト**  
   - JavaScriptでマウス座標を取得し、粒子（`.particle`）を追従させる仕組みを実装。  
   - （※実際の粒子要素はHTMLに追加していますが、数は最小限に抑えています）

4. **ページ遷移**  
   - CSSトランジションで滑らかなフェードアウト/インを実現。

---

このコードは、**「Sarashina miniの紹介」というテーマに沿ったデザインと、ユーザーの操作に応じた動的な反応**を組み合わせた例です。  
ご希望があれば、特定の機能（例：チャットボット、3Dモデル表示）を追加したり、デザインのトーンを調整したりすることも可能です。  
何か修正点や追加したい要素があれば、お気軽にお知らせくださいね！
