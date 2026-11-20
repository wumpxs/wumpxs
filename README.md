<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1b27,100:7aa2f7&height=130&section=header&text=Hey%20👋,%20ik%20ben%20Wumpxs!&fontSize=36&fontColor=ffffff&animation=fadeIn&fontAlignY=38" />
  
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=20&pause=1000&color=7AA2F7&center=true&vCenter=true&width=580&lines=Software+Development+Student+%40+ROC+Hilversum;Full-Stack+Web+Developer+in+de+maak;FiveM+Scripter+(Lua+5.4)%20%7C%20Vue+%26+Supabase" alt="Typing SVG" />
  </a>

  <p>
    <img src="https://komarev.com/ghpvc/?username=Wumpxs&label=Profile%20views&color=7aa2f7&style=for-the-badge" alt="Profile views" />
    <img src="https://img.shields.io/badge/Focus-Vue%20%26%20Supabase-42b883?style=for-the-badge&logo=vue.js&logoColor=white" />
    <img src="https://img.shields.io/badge/Scripting-FiveM%20Lua%205.4-f40552?style=for-the-badge&logo=lua&logoColor=white" />
    <img src="https://img.shields.io/badge/Status-Open%20voor%20projecten-7aa2f7?style=for-the-badge" />
  </p>
</div>

---

<div align="center">

## 👨‍💻 Over mij

Ik ben een eerstejaarsstudent **Software Development** aan het **ROC Hilversum** met een grote passie voor bouwen, experimenteren en problemen oplossen met code. Of het nu gaat om een strakke webapplicatie of een custom script voor FiveM: ik vind het geweldig om ideeën vanaf nul werkend te krijgen.

<br>

| 💡 Categorie | 📝 Details |
| :--- | :--- |
| 🎓 **Opleiding** | Software Development (Jaar 1) — ROC Hilversum |
| 💻 **Wat ik graag bouw** | Moderne websites, webshops en custom FiveM scripts |
| 🛒 **Huidig project** | Een complete full-stack webshop bouwen voor school |
| 🌱 **Focus op dit moment** | Front-end bouwen met **Vue** & data opslaan in **Supabase** |
| 🎮 **FiveM & Gaming** | Scripten in **Lua 5.4** (mechanics, UI's en server-optimalisatie) |
| 🧠 **Mijn mindset** | *Learning by doing* — fouten maken hoort erbij, elke bug maakt je beter |
| ⚡ **Code stijl** | Clean, overzichtelijk en altijd op zoek naar slimme oplossingen |
| 🔥 **Waar ik energie van krijg** | Een lastige bug oplossen en een nieuw systeem live zien werken |
| 🛵 **Buiten het coderen** | Vaak te vinden op mijn scooter om te stunten en te chillen met vrienden |
| 🤝 **Samenwerken** | Sta altijd open voor nieuwe projecten, feedback of samen coden |

<br>

> 💬 *"Van een leeg bestand naar een werkende applicatie — dat is waarom ik code."*

</div>

---

<div align="center">

## 🧭 Hoe ik werk & waar ik op focus

<table>
  <tr>
    <td width="50%" valign="top">
      <h3 align="center">🎮 FiveM & Server Logic</h3>
      <ul>
        <li>Modulaire resource-structuur in <b>Lua 5.4</b></li>
        <li>Strakke <b>resmon</b> (0.00ms idle) & server-side validatie</li>
        <li>Custom <b>NUI</b> interfaces met HTML, CSS & JS</li>
        <li>Event-driven architectuur & anti-exploit checks</li>
      </ul>
    </td>
    <td width="50%" valign="top">
      <h3 align="center">🌐 Full-Stack Web Apps</h3>
      <ul>
        <li>Component-based UI's bouwen in <b>Vue 3</b> & <b>Tailwind</b></li>
        <li>Authenticatie, PostgreSQL & Realtime via <b>Supabase</b></li>
        <li>Clean database-schema's & herbruikbare composables</li>
        <li>Responsive design van schets in <b>Figma</b> tot live deploy</li>
      </ul>
    </td>
  </tr>
</table>

</div>

---

<div align="center">

## ⚡ Onder de motorkap (Code Snippets)

*Klik open om te zien hoe ik zowel FiveM resources als moderne webapps opbouw:*

</div>

<details open>
  <summary><b>🎮 FiveM Resource Runtime — <code>wumpxs_core/server/main.lua</code></b></summary>

```lua
local Developer = {}
Developer.__index = Developer

local STACK <const> = {
    lua      = { version = "5.4", role = "FiveM Server/Client & NUI" },
    vue      = { version = "3.x", role = "Reactive Frontend" },
    supabase = { role = "Postgres / Auth / Realtime" },
    web      = { "HTML5", "CSS3", "Tailwind", "PHP", "MySQL" }
}

function Developer.new(profile)
    return setmetatable({
        user       = profile.user or "Wumpxs",
        school     = "ROC Hilversum — Software Dev (Y1)",
        mood       = profile.mood or "locking_in",
        bugsSolved = 0,
        stack      = STACK
    }, Developer)
end

local function ship(task)
    if task.broken then
        error(("Bug caught in [%s]: %s"):format(task.module, task.reason), 0)
    end
    task.deployed = true
    return ("SHIPPED :: %s -> production"):format(task.module)
end

function Developer:runPipeline(tasks)
    for _, task in ipairs(tasks) do
        local ok, result = xpcall(ship, debug.traceback, task)
        while not ok do
            self.bugsSolved = self.bugsSolved + 1
            task.broken = false
            ok, result = xpcall(ship, debug.traceback, task)
        end
        print(result)
    end
    return ("Done. Bugs squashed: %d"):format(self.bugsSolved)
end

CreateThread(function()
    local wumpxs = Developer.new({ user = "Wumpxs", mood = "building" })
    local output = wumpxs:runPipeline({
        { module = "fivem-garage-nui",  broken = true,  reason = "NUI focus stuck" },
        { module = "vue-supabase-shop", broken = false, reason = nil }
    })
    TriggerEvent("wumpxs:status", output)
end)
```

</details>

<details>
  <summary><b>🛒 Webshop Composable — <code>useProducts.js</code> (Vue 3 + Supabase)</b></summary>

```javascript
import { ref, computed } from 'vue'
import { supabase } from '@/lib/supabase'

export function useProducts() {
  const products = ref([])
  const loading = ref(false)
  const error = ref(null)

  const inStockProducts = computed(() =>
    products.value.filter((item) => item.stock > 0)
  )

  async function fetchCatalog(category = null) {
    loading.value = true
    error.value = null

    let query = supabase
      .from('products')
      .select('id, name, price, stock, category, image_url')
      .order('created_at', { ascending: false })

    if (category) query = query.eq('category', category)

    const { data, error: sbError } = await query
    if (sbError) error.value = sbError.message
    else products.value = data ?? []

    loading.value = false
  }

  return { products, inStockProducts, loading, error, fetchCatalog }
}
```

</details>

---

<div align="center">

## 🛠️ Tech Stack & Tools

### 💻 Talen & Frameworks die ik beheers
<a href="https://skillicons.dev">
  <img src="https://skillicons.dev/icons?i=html,css,tailwind,php,lua" />
</a>

### 📚 Waar ik nu mee bezig ben
<a href="https://skillicons.dev">
  <img src="https://skillicons.dev/icons?i=vue,supabase,js" />
</a>

### ⚙️ Tools & Software die ik gebruik
<a href="https://skillicons.dev">
  <img src="https://skillicons.dev/icons?i=vscode,git,github,figma,mysql" />
</a>

</div>

---

<div align="center">

## 🚀 Uitgelichte Projecten & Focus

| Project / Categorie | Beschrijving | Tech Stack | Status |
| :--- | :--- | :--- | :--- |
| 🛍️ **School Webshop** | Complete webshop met productoverzicht, winkelwagen en database-koppeling. | `Vue` `Tailwind` `Supabase` | 🚧 In ontwikkeling |
| 🎮 **FiveM Scripts** | Custom server- en client-side scripts, NUI interfaces en game mechanics. | `Lua 5.4` `HTML/CSS` `FiveM` | ✅ Actief |
| 🌐 **Web Development** | Snelle, responsive websites en back-end opdrachten voor school. | `HTML` `CSS` `PHP` `Tailwind` | ✅ Actief |
| 🧪 **Sandbox & Experimenten** | Kleine testprojecten om nieuwe packages, databases en designs uit te proberen. | `Vue` `Supabase` `Git` | 🔄 Doorlopend |

<br>

### 📌 Uitgelichte Repositories
> 💡 *Vervang `Wumpxs` bij `repo=` door de naam van je eigen repo zodra je projecten openbaar staan.*

<a href="https://github.com/Wumpxs">
  <img src="https://github-readme-stats.vercel.app/api/pin/?username=Wumpxs&repo=Wumpxs&theme=tokyonight&hide_border=true" />
</a>

</div>

---

<div align="center">

## 🎯 Roadmap & Doelen

- [x] De basis van HTML, CSS, Tailwind & PHP onder de knie krijgen
- [x] Eigen scripts schrijven in Lua 5.4 voor FiveM
- [ ] Mijn eerste volledige **Vue + Supabase** webshop afronden
- [ ] Meer open-source projecten en eigen code op GitHub delen
- [ ] Mijn eigen portfolio-website ontwerpen en online zetten
- [ ] Doorgroeien tot een allround **Full-Stack Developer**

</div>

---

<div align="center">

## 🏆 GitHub Trophies

<img src="https://github-profile-trophy.vercel.app/?username=Wumpxs&theme=tokyonight&no-frame=true&no-bg=true&row=1&column=6" />

</div>

---

<div align="center">

## 📊 GitHub Statistieken & Activiteit

<img height="180em" src="https://github-readme-stats.vercel.app/api?username=Wumpxs&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true" />
<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Wumpxs&layout=compact&theme=tokyonight&hide_border=true" />

<br><br>

<img src="https://streak-stats.demolab.com?user=Wumpxs&theme=tokyonight&hide_border=true" alt="GitHub Streak" />

<br><br>

<img src="https://github-readme-activity-graph.vercel.app/graph?username=Wumpxs&theme=tokyo-night&hide_border=true&area=true" width="90%" />

</div>

---

<div align="center">

## 💭 Random Dev Quote

<img src="https://quotes-github-readme.vercel.app/api?type=horizontal&theme=tokyonight" alt="Random Dev Quote" />

<br><br>

## 📫 Contact & Connect

<p>
  <a href="https://github.com/Wumpxs">
    <img src="https://img.shields.io/badge/GitHub-Wumpxs-181717?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://discord.com">
    <img src="https://img.shields.io/badge/Discord-Wumpxs-5865F2?style=for-the-badge&logo=discord&logoColor=white" />
  </a>
</p>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1b27,100:7aa2f7&height=100&section=footer" />

</div>
