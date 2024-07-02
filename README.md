<!-- @format -->


# Setting up simple build proccess

[Udemy video](https://www.udemy.com/course/advanced-css-and-sass/learn/lecture/8274568#overview)

#### 1. Enne kui alustad:

- Veendu, et oleks olemas `package.json` fail. Seal sees oluline info, et mida vaja installida npm-ga.
- Muuda ära `package.json` failis need väljad kus jutumärkides "vaja-muuta" kirjas on.

#### 2. Node Moodulite intallimine

- Ava VS Code Terminal: Terminal --> New Terminal
- Installi node_module folder ja kõik muud vajalikud seosed: `npm i` või kui error tuleb siis `sudo npm i`
  - see installib kõik seosed ja node moodulid (kui node_modules ei ilmu siis tee VS Code restart)

#### 3. Käivida dev server

- Kasuta selleks scripti: `npm run start`
- Nüüd näitab Terminal url-i (nt: http://127.0.0.1:8080) mis ava browseris. Ühtlasi on url-i ilmumine ka märk, et kõik õnnestus ja dev-server script package.json failis on edukalt käivitunud.

#### 4. Lõppfaili, CSS faili loomine

- Kui vaja lõppfail serverisse saata siis enne tee sellest "build" fail. Kasuta selleks käsklust: `npm run build:css`. Selleks pead avama uue Terminal akna kuna live-server või mõni muu script käib praeguses aktiivses Terminalis.
- Lõppfail mis lae serverisse tekib folderis: css => styel.css.

#### Näidis json faili sisu.

```json
{
	"name": "swissotel_landing_1",
	"version": "1.0.0",
	"description": "Easy landingpage",
	"main": "index.js",
	// UUE PROJEKTI JAOKS COPY SEE ALATES SIIT -->
	"scripts": {
		"watch:sass": "node-sass sass/main.scss css/style.css -w",
		"devserver": "live-server --browser=chrome",
		"start": "npm-run-all --parallel devserver watch:sass",
		"compile:sass": "node-sass sass/main.scss css/style.comp.css",
		"prefix:css": "postcss --use autoprefixer -b 'last 10 versions' css/style.comp.css -o css/style.prefix.css",
		"compress:css": "node-sass css/style.prefix.css css/style.css --output-style compressed",
		"build:css": "npm-run-all compile:sass prefix:css compress:css"
		// <--  UUE PROJEKTI JAOKS COPY SEE KUNI SIIT
	},
	"author": "Highway Media OÜ",
	"license": "ISC",
	"devDependencies": {
		// UUE PROJEKTI JAOKS COPY SEE ALATES SIIT -->
		"node-sass": "^5.0.0",
		"autoprefixer": "^7.1.4",
		"concat": "^1.0.3",
		"npm-run-all": "^4.1.1",
		"postcss-cli": "^4.1.1"
		// <--  UUE PROJEKTI JAOKS COPY SEE KUNI SIIT
	}
}
```
# test10
