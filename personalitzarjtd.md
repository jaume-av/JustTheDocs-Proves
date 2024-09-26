Per **personalitzar l'aparença** d'un lloc web creat amb **Just the Docs**, hi ha diverses opcions que et permetran modificar l'estil del tema, com ara afegir **CSS personalitzat**, modificar els colors, la tipografia, l'estructura de la pàgina, i més.

A continuació, et mostro com pots personalitzar l'aparença de la teva pàgina **Just the Docs**.

---

### **1. Personalitzar l'aparença amb CSS personalitzat**

Just the Docs et permet afegir CSS personalitzat per modificar l'estil de la teva pàgina. Aquests són els passos per afegir el teu propi CSS:

#### **Pas 1: Crear un fitxer de CSS personalitzat**

1. Crea una carpeta dins del teu repositori anomenada **`assets/css/`** (si no existeix ja).

2. Dins d'aquesta carpeta, crea un fitxer anomenat **`custom.css`**.

3. Afegeix les regles de **CSS** que vulguis per personalitzar l'estil del teu lloc web. Per exemple, per canviar els colors dels enllaços i el fons de la pàgina:

   ```css
   /* Canvia el color dels enllaços */
   a {
     color: #3498db;
   }

   /* Canvia el fons de la pàgina */
   body {
     background-color: #f5f5f5;
   }

   /* Personalitza els títols */
   h1, h2, h3, h4 {
     font-family: 'Arial', sans-serif;
     color: #2c3e50;
   }
   ```

#### **Pas 2: Incloure el CSS personalitzat en el lloc**

1. Ara has d'informar **Just the Docs** que utilitzi aquest fitxer **`custom.css`**. Per fer-ho, edita el fitxer **`_config.yml`** i afegeix-hi el següent:

   ```yaml
   # Afegeix el fitxer CSS personalitzat
   include:
     - assets/css/custom.css
   ```

2. També has d'assegurar-te que el teu CSS personalitzat es carregui a la pàgina. Per fer-ho, obre el fitxer **`_includes/head_custom.html`** (o crea'l si no existeix) i afegeix el següent codi dins de la capçalera:

   ```html
   <link rel="stylesheet" href="{{ '/assets/css/custom.css' | relative_url }}">
   ```

3. Si aquest fitxer **`head_custom.html`** no existeix, crea'l dins d'una carpeta **`_includes/`** a l'arrel del teu projecte.

#### **Pas 3: Puja els canvis**

Un cop hagis creat el fitxer **`custom.css`** i l'hagis inclòs al fitxer de configuració, puja tots els canvis al repositori:

```bash
git add .
git commit -m "Afegit CSS personalitzat"
git push origin main
```

---

### **2. Personalitzar els colors del tema Just the Docs**

Si vols personalitzar els colors principals del tema **Just the Docs**, pots utilitzar variables de CSS per sobreescriure els colors predeterminats.

#### **Exemple de personalització de colors amb CSS:**

1. Al fitxer **`custom.css`**, pots afegir regles per modificar els colors predeterminats del tema:

   ```css
   /* Canvia el color del text */
   :root {
     --color-text-primary: #333333;
     --color-text-secondary: #4a4a4a;
   }

   /* Canvia el color dels enllaços */
   a {
     color: #ff5733;
   }

   /* Canvia el color de fons de la pàgina */
   body {
     background-color: #f0f0f0;
   }
   ```

2. Les variables de **CSS** prefixades amb **`--`** són part de l'especificació CSS, i **Just the Docs** ja inclou algunes per facilitar la personalització. Pots redefinir qualsevol d'aquestes variables per canviar l'aparença del lloc.

   Alguns exemples de variables de color que pots modificar:
   - **`--color-text-primary`**: Color del text principal.
   - **`--color-text-secondary`**: Color del text secundari.
   - **`--color-bg-primary`**: Color de fons principal.
   - **`--color-link`**: Color dels enllaços.

#### **Exemple complet d'un CSS personalitzat per colors:**

```css
:root {
  /* Colors del text */
  --color-text-primary: #1a1a1a;
  --color-text-secondary: #555555;

  /* Color dels enllaços */
  --color-link: #1e90ff;
  --color-link-hover: #ff4500;

  /* Colors de fons */
  --color-bg-primary: #fafafa;
  --color-bg-secondary: #f5f5f5;
}

/* Canvia l'estil dels títols */
h1, h2, h3 {
  color: #2c3e50;
  font-family: 'Arial', sans-serif;
}
```

---

### **3. Personalitzar la tipografia**

Si vols utilitzar una tipografia diferent, pots afegir fonts personalitzades des de **Google Fonts** o qualsevol altre proveïdor de fonts.

#### **Pas 1: Incloure una font de Google Fonts**

1. Primer, afegeix la font al teu fitxer **`custom.css`** o dins del fitxer **`_includes/head_custom.html`**. Per exemple, per afegir la font **Roboto**:

   ```html
   <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
   ```

2. Després, pots aplicar aquesta font a tot el lloc o només a parts específiques del lloc.

#### **Pas 2: Aplicar la font a diferents elements**

1. Al fitxer **`custom.css`**, afegeix regles per aplicar la font a tot el lloc:

   ```css
   /* Aplicar la font Roboto a tot el lloc */
   body {
     font-family: 'Roboto', sans-serif;
   }

   /* Aplicar la font a elements específics */
   h1, h2, h3, h4, h5 {
     font-family: 'Roboto', sans-serif;
   }
   ```

---

### **4. Personalitzar la navegació lateral**

Pots modificar la navegació lateral (sidebar) i l'ordre en què es mostren els enllaços configurant el fitxer **`_config.yml`** o afegint configuracions personalitzades a les pàgines.

#### **Configurar l'ordre de la navegació**

Per canviar l'ordre dels elements a la barra lateral, pots utilitzar la propietat **`nav_order`** als teus fitxers **`.md`**.

1. Al fitxer **`index.md`** o altres fitxers Markdown:
   ```yaml
   ---
   title: Home
   layout: default
   nav_order: 1
   ---
   ```

2. Afegeix el valor de **`nav_order`** per cada pàgina per controlar l'ordre en què apareixen a la barra lateral.

---

### **5. Utilitzar fragments de codi personalitzats (components de Jekyll)**

Si vols afegir fragments de codi personalitzats o components reutilitzables a les teves pàgines, pots utilitzar la funcionalitat d'**inclusió de fitxers** de Jekyll.

1. Crea un fitxer dins de la carpeta **`_includes`** anomenat **`custom_component.html`**:
   ```html
   <div class="custom-box">
     <h2>{{ include.title }}</h2>
     <p>{{ include.content }}</p>
   </div>
   ```

2. Afegeix aquest component dins d'un fitxer Markdown, indicant el títol i el contingut:
   ```markdown
   {% include custom_component.html title="Benvingut" content="Aquesta és una caixa personalitzada." %}
   ```

---

### **Conclusió**

Amb aquests passos, pots personalitzar l'aparença del teu lloc **Just the Docs** de moltes maneres: canviant colors, tipografies, disseny, i molt més. Les opcions són molt flexibles gràcies a l'ús de **CSS personalitzat** i la integració amb **Jekyll**, el que et permet afegir elements molt més avançats si ho necessites.

Si necessites ajuda per afegir una personalització concreta, només has de preguntar!