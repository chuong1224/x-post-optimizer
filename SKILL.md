---
name: x-post-optimizer
version: 2.0.0
description: Kich hoat khi user upload video hoac anh nhan vat fantasy va yeu cau viet post X tieng Anh ngan gon toi uu tang reach. BAT CU KHI NAO user noi: viet post X, viet post tieng Anh ngan gon, toi uu reach, post for X, write X post, ngan gon hon, shorten this post, optimize X post, tang reach X. Vi du: user upload video roi goi viet post tieng Anh ngan gon toi uu tang reach la skill tu dong phan tich va xuat post chuan. Skill con xu ly ngan gon hon de lap lai qua trinh rut gon. Khong kich hoat khi user chi hoi kien thuc ve X algorithm, yeu cau viet caption mang xa hoi khac, hoac khong co video hoac hinh anh duoc upload kem.
---

# X Post Optimizer

## Muc dich
Chuyen doi video/anh nhan vat fantasy thanh post X tieng Anh ngan gon, toi uu reach thong qua reply-weighted engagement (tin hieu cao nhat trong X algorithm).

---

## Workflow

### Buoc 1 — Phan tich Visual
Quan sat ky toan bo frames. Trich xuat theo thu tu uu tien:
- **Ngoai hinh**: mau toc, mau mat, bieu cam, chi tiet da
- **Trang phuc/giap**: mau sac, phong cach (corset, kimono, armor, wings)
- **Vu khi/prop**: kiem, khien, staff, glow effects
- **Boi canh**: temple, cathedral, burning city, cosmic void
- **Hieu ung**: glow, lightning, fire, petals, feathers, particles
- **Vibe tong the**: dark / ethereal / powerful / seductive / vengeful / regal

### Buoc 2 — Chon Character Title
Khop visual voi bang duoi. Neu khong khop → ghep theo cong thuc: [Hair Color] + [Key Feature] + [Archetype]

| Visual Combination | Character Title |
|---|---|
| Silver hair + blood kimono + red katanas | Crimson Sakura Onna |
| Blonde + large pink/white wings + cathedral | Fallen Seraph / Celestial Seraph |
| Blue-silver hair + lightning sword + vortex | Lightning Seraph |
| Blonde + black-gold armor + lion shield | Golden Rose Queen |
| White hair + red eyes + flaming sword | Fire Queen / Scarlet Blade Princess |
| Dark hair + purple robe + void energy | Shadow Empress |
| Gold hair + white armor + holy light | Divine Valkyrie |
| Red hair + dragon scales + fire wings | Infernal Dragon Queen |

### Buoc 3 — Tao Post theo Structure Chuan
Ap dung chinh xac cau truc sau:

```
[Emoji1][Emoji2] [Hook — max 10 words]

[1-2 dong mo ta visual noi bat + Character Title]

If she looked at you [through the flames/storm/void/dark] and said "[command verb]"… would you?

Drop your answer below — I'm reading every reply 🔥
```

**Rang buoc bat buoc:**
- Tong do dai PHAI <= 280 ky tu (ke ca spaces + line breaks ~4 ky tu moi dong)
- Dong 1: Hook manh + 1-2 emoji phu hop vibe
- Dong 2-3: Chi mo ta visual noi bat nhat + character title
- Dong 4: Cau hoi ca nhan + verb manh + ellipsis
- Dong 5: LUON LUON la `Drop your answer below — I'm reading every reply 🔥`

### Buoc 4 — Xu ly "ngan gon hon"
- Giu nguyen toan bo structure (khong bo tang nao)
- Chi rut gon dong mo ta: bo chi tiet thu cap (mau mat, hieu ung phu)
- KHONG xoa CTA dong cuoi
- KHONG xoa hook dong dau
- KHONG xoa cau hoi cam xuc

### Buoc 5 — Output
- Xuat DUNG POST TEXT, khong them gi
- Khong co giai thich, khong co meta comment
- Neu la rut gon: chi xuat version ngan hon, khong xuat ca 2

---

## Hook Templates

| Mood | Hook |
|---|---|
| Vengeful | She doesn't fight for honor. She fights for [blood/revenge]. |
| Seductive | She doesn't ask for [permission/mercy]. She [takes/commands]. |
| Divine | She doesn't save souls. She claims them. |
| Powerful | She doesn't need an army. She is the storm. |
| Dark | She wasn't born a monster. She was made. |

## Question Templates

| Setting | Question |
|---|---|
| Flames | If she looked at you through the flames and said "Follow me"… would you? |
| Storm | If she appeared in the storm and said "Kneel"… would you? |
| Darkness | If she found you in the dark and said "Stay"… would you? |
| Battle | If she stood over you after battle and said "Rise"… would you? |
| Void | If she pulled you into the void and said "Trust me"… would you? |

---

## Examples

**Full version (~230 chars):**
```
⚔️🌸 She doesn't fight for honor. She fights for blood.

Silver hair glowing, blood-stained kimono, twin red katanas raised. The Crimson Sakura Onna has risen.

If she looked at you with those burning eyes and said "Draw your blade"… would you?

Drop your answer below — I'm reading every reply 🔥
```

**Shortened version (~175 chars):**
```
✨🪡 She doesn't save souls. She claims them.

Blonde hair, massive wings spread wide. The Fallen Seraph has descended.

If she looked at you and said "Come closer"… would you?

Drop your answer below — I'm reading every reply 🔥
```

**Ultra-short version (~140 chars):**
```
⚡🗡️ She commands the storm.

Lightning Seraph. Silver hair. Blue flowing dress.

If she said "Kneel"… would you?

Drop your answer below — I'm reading every reply 🔥
```

---

## Gotchas

1. **Dem sai ky tu**: Line breaks (\n) tinh la ~4 ky tu moi dong — 4 dong tuc la mat ~16 ky tu, de bi vuot 280
2. **Emoji sai vibe**: Dung emoji khop mood — ⚔️🌸 cho samurai, ✨🪡 cho angel, ⚡ cho lightning, 🔥 cho fire queen — tuyet doi khong dung emoji cute (😊💕) cho nhan vat dark/powerful
3. **Mo ta qua dai**: Neu vuot 280 chars, uu tien cat chi tiet mat/boi canh truoc, giu vu khi va character title
4. **Quen CTA**: `Drop your answer below — I'm reading every reply 🔥` phai LUON o dong cuoi, nguyen van, khong rut gon, khong thay the
5. **Character title generic**: "Warrior", "Fighter", "Hero" = yeu — phai co tinh rieng (Crimson Sakura Onna, Lightning Seraph); neu khong khop bang → tu ghep theo cong thuc
6. **Cau hoi nhat ban**: "Would you fight her?" rat thap reply — cau hoi phai ca nhan hoa + verb co suc manh cam xuc (Kneel, Stay, Follow me, Draw your blade)
7. **Output kem meta comment**: Tuyet doi khong xuat "Day la post:", "Post toi uu:", hay bat ky giai thich nao — chi xuat raw post text