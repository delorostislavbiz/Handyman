# TASK: Align Prototype with Sitemap

## Reference Files
- Sitemap: `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/handyman_nj_sitemap.md`
- Design reference: `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/services/tv-mounting.html` (for services)
- City reference: `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/bergen/hackensack.html` (for cities)

---

## TASK 1: Fix City Pages

### Problem
Two cities in prototype don't match sitemap:

| Current (wrong) | Should be (correct) |
|-----------------|---------------------|
| morris/madison.html | morris/randolph.html |
| essex/maplewood.html | essex/west-orange.html |

### Instructions

1. **Delete** wrong files:
   - `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/morris/madison.html`
   - `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/locations/essex/maplewood.html`

2. **Create** correct files by copying similar city page and updating:
   - Copy `morristown.html` → create `randolph.html`
   - Copy `montclair.html` → create `west-orange.html`

3. **Update content** in new files:
   - Replace all city name references (Madison → Randolph, Maplewood → West Orange)
   - Update population data from sitemap
   - Update `<title>` and `<meta>` tags
   - Update H1 heading
   - Keep same Tailwind CSS structure

### Randolph Data (from sitemap)
- City: Randolph
- County: Morris County
- Population: 25,000
- URL: randolph.html

### West Orange Data (from sitemap)
- City: West Orange
- County: Essex County
- Population: 47,000
- URL: west-orange.html

---

## TASK 2: Fix Service Pages

### Problem
Prototype has 8 services, sitemap requires 12:

**Currently exist (keep):**
1. tv-mounting.html
2. furniture-assembly.html
3. painting.html
4. drywall-repair.html
5. plumbing.html
6. electrical.html
7. smart-home.html

**Delete:**
- general-repairs.html (not in sitemap)

**Create new (5 pages):**
1. tile-installation.html
2. carpentry.html
3. flooring.html
4. deck-repair.html
5. doors-windows.html

### Instructions

1. **Delete** `/mnt/d/ПРОЕКТЫ_V2/VASILI_2/prototype/services/general-repairs.html`

2. **Create 5 new service pages** using existing service page as template

3. **For each new page:**
   - Copy structure from `painting.html` or `drywall-repair.html`
   - Update service name in `<title>`, `<meta>`, H1
   - Update service description content
   - Keep same Tailwind CSS classes
   - Keep same navigation, header, footer
   - Update FAQ section with relevant questions

### New Service Details

#### tile-installation.html
- Title: Tile Installation Services in Northern NJ
- H1: Professional Tile Installation in Northern New Jersey
- Focus: Bathroom, kitchen, floor tiles, backsplash

#### carpentry.html
- Title: Carpentry Services in Northern NJ
- H1: Professional Carpentry Services in Northern New Jersey
- Focus: Custom woodwork, trim, molding, shelving, repairs

#### flooring.html
- Title: Flooring Installation in Northern NJ
- H1: Professional Flooring Installation in Northern New Jersey
- Focus: Hardwood, laminate, vinyl, floor repairs

#### deck-repair.html
- Title: Deck Repair Services in Northern NJ
- H1: Professional Deck Repair in Northern New Jersey
- Focus: Deck boards, railings, staining, structural repairs

#### doors-windows.html
- Title: Door & Window Services in Northern NJ
- H1: Door and Window Installation in Northern New Jersey
- Focus: Interior/exterior doors, window installation, hardware

---

## Design System Reference

### Tailwind Config (copy from existing pages)
```html
<script src="https://cdn.tailwindcss.com"></script>
<script>
    tailwind.config = {
        theme: {
            extend: {
                colors: {
                    'brand': {
                        50: '#fffbeb', 100: '#fef3c7', 200: '#fde68a', 300: '#fcd34d',
                        400: '#fbbf24', 500: '#f59e0b', 600: '#d97706', 700: '#b45309',
                    }
                },
                fontFamily: {
                    'display': ['"DM Serif Display"', 'Georgia', 'serif'],
                    'body': ['"Source Sans 3"', 'system-ui', 'sans-serif'],
                }
            }
        }
    }
</script>
```

### Key Classes
- Body: `bg-slate-950 text-slate-300 font-body`
- Headings: `font-display text-white`
- Brand color: `text-brand-500`, `bg-brand-500`
- Cards: `bg-slate-900 border border-slate-800 rounded-xl`
- Buttons: `bg-brand-500 hover:bg-brand-600 text-slate-900`

### Paths
- Services: `../` for relative links to root
- Cities: `../../` for relative links to root

---

## Checklist

### Cities
- [ ] Delete madison.html
- [ ] Delete maplewood.html
- [ ] Create randolph.html
- [ ] Create west-orange.html

### Services
- [ ] Delete general-repairs.html
- [ ] Create tile-installation.html
- [ ] Create carpentry.html
- [ ] Create flooring.html
- [ ] Create deck-repair.html
- [ ] Create doors-windows.html

### Verification
- [ ] All 12 service pages exist
- [ ] All 25 city pages exist with correct names
- [ ] All pages use Tailwind CSS
- [ ] All navigation links work

---

## IMPORTANT RULES

1. **DO NOT change text** in existing pages
2. **Copy structure exactly** from reference files
3. **Use same Tailwind classes** as existing pages
4. **Test navigation links** after changes
