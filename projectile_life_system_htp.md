Projectile Life System (HTP)

A micro-framework that fixes one of the biggest flaws in RPG/ARPG/MMO combat.


---

Core Idea

Every skill/projectile has its own HP (Life).
It decays over distance, can be damaged, can clash with other skills, and can be drained.

Biến projectile từ “object vô tri” → thành entity sống với tương tác thực chiến.


---

Core Mechanics

1. Skill HP (Life)

Mỗi skill có một chỉ số:

SkillLife = BaseLife × (UserMagicPowerScaling)

HP này đại diện cho độ bền năng lượng.


---

2. Distance Decay

Skill mất dần HP khi bay xa:

HP_loss = Distance × DecayRate

→ Skill yếu dần, không thể bay vô hạn.


---

3. Projectile Clash

Khi 2 skill chạm nhau:

Skill A Life > Skill B Life → A xuyên qua (Life = LifeA – LifeB)

Skill A Life < Skill B Life → A bị phá

Life ngang nhau → cả hai nổ tại chỗ



---

4. Projectile Damage Taken

Mọi nguồn damage có thể giảm Life của skill:

đạn

spell khác

vũ khí chém trúng skill

trap

aura

terrain


→ Combat có chiều sâu gấp nhiều lần.


---

5. Skill Drain (Energy Leech)

Skill của người chơi có thể hút Life từ skill đối thủ để:

tăng damage

tăng thời gian tồn tại

tăng kích thước

đổi thuộc tính (nếu đủ Life)



---

6. Death Behavior

Khi SkillLife = 0 → skill chết:

nổ

tan

phân rã thành energy

tạo secondary effect (nếu design cho phép)



---

Example

Fireball

BaseLife: 100

DecayRate: 2 HP/m

Travel: 30m
→ mất 60 HP
→ còn 40 HP khi đến mục tiêu


Nếu nó gặp Ice Lance (Life = 50):

Ice Lance (50) > Fireball (40) → Fireball bị phá, Ice Lance còn 10.


---

Lightning Beam (drain)

Beam hút 5 HP/s từ skill gần đó.
Nếu beam chạm 3 projectile:

3 × 5 = 15 HP/s
Beam dày hơn, damage tăng.



---

Notes

Micro-framework nhưng mở ra hệ combat hoàn toàn mới.

Phù hợp với RPG / ARPG / MMO / MOBA / Shooter fantasy.

Dễ code thử: chỉ cần thêm Life vào projectile class.

Tạo ra counterplay: “fight skill bằng skill”.

Tương thích 100% với Relative Defense và Armor Layer của HTP.

Là bước đệm để làm “Spell Ecosystem” — nơi skill sống như sinh vật năng lượng.



---

Author

HTP

Twitter/X:

https://x.com/AloName15

Donate (Buy me bún bò):

https://buymeacoffee.com/chaoshtp

Public domain. Use freely.