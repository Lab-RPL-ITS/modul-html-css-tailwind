# Tailwind 

# Table of contents

- [Table of contents](#table-of-contents)
- [Intro](#intro)
  - [Requirement](#requirement)
  - [Tailwind Documentation](#tailwind-documentation)

- [Setup](#setup)
  - [Instalation](#installation)
- [Referensi](#referensi)

# Intro

Apa itu Tailwind? 
> ### Rapidly build modern websites without ever leaving your HTML. 
A utility-first CSS framework packed with classes like flex, pt-4, text-center and rotate-90 that can be composed to build any design, directly in your markup 
>
>~ [tailwindcss.com](https://tailwindcss.com/)

 
Tailwind CSS merupakan sebuah *utility-first CSS framework*. Tailwind dapat diibaratkan sebagai kerangka kerja yang akan memudahkan penggunanya dalam melakukan *styling* pada web dengan menggunakan CSS.

Tailwind akan menyediakan `class` utilitas yang dapat kita gunakan langsung dari HTML seperti class `pt-3` untuk menambahkan padding sebesar 16px, `text-center` untuk membuat teks rata tengah (justify) dan masih banyak class-class utilitas lainnya.

Dengan memanfaat class-class utitlitas dari Tailwind kita dapat dengan mudah melakukan *styling* langsung dari file HTML tanpa harus berpindah-pindah antara file HTML dengan file CSS.

## Requirement

Sebelum mempelajari course Tailwind ini, kamu diharapkan memahami dasar materi di bawah:
- HTML
- CSS

## Tailwind Documentation

Sebelum mulai untuk menggunakan Tailwind, kita harus mengenal dokumentasi milik Tailwind terlebih dahulu. Dokumentasi Tailwind ini digunakan sebagai panduan kita dalam menggunakan Tailwind, oleh karena itu dalam penggunaannya nanti kita akan sering melibatkan dokumentasi Tailwind tersebut. 
Dokumentasi tailwind dapat di akses pada website resmi Tailwind https://tailwindcss.com/docs 

# Setup
## Installation
Setidaknya terdapat 4 cara/panduan utama dalam untuk melakukan instalasi tailwind:
1. Tailwind CLI (Command Line Interface)
2. Play CDN (content delivery network)
3. Menggunakan PostCSS
4. Mengikuti Panduan untuk suatu Framework tertentu

Dalam kesempatan kali ini, kita akan menggunakan 2 cara yang paling mudah dan cepat untuk dilakukan yaitu dengan Tailwind CLI dan Play CDN.

- #### Tailwind CLI [(⌐■_■)](https://tailwindcss.com/docs/installation)
- #### Play CDN [(⊙_⊙;)](https://tailwindcss.com/docs/installation/play-cdn)

Untuk mempermudah penggunaan Tailwind, sangat direkomendasikan untuk menggunakan *extension* [Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) (untuk vscode)


# note
Setting up tailwind 2.0/ installation

terdapat 2 cara umum untuk melakukan instalasi tailwind pada suatu proyek
1. CDN
Penggunaan CDN cukup mudah hanya perlu untuk menambahkan link tag cdn tailwing yang telah disediakan pada head html.
 - belum ada postcss atau rekomendasi

2. Tailwind CSS CLI (Command Line Interface)
	1. membuat file css sendiri
	2. "@tailwind base" -> base directive -> reset
	3. "@tailwind components" directive -> essenctially a responsive max-width container
	4. "@taileind utilities" directive -> layer paling utama yang berisis class-class yang akan banyak digunakan dalam menggunakan css
	5. npx tailwind-cli build css/taileind.css -o build/tailwind.css (membuat input dan output file)
	6 tailwind directive -> tailwind layer 
	7. outpu file akan berubah sesuai isi dari input file setiap di postcss dijalankan
- menggunakan vite 
	npm init -y
	npm i -D tailwind css postcss autoprefixer vite
	- scripts -> dev -> vite
generate 2 config file dengan npx tw init -p
postcss config
- linkkan link di html ke tailwind.css
- npm run dev


The utility-first workflow
menggunakan semua layer utilities yang telah disediakan oleh tailwind
(project-base membuat page)
-> layouting, sizing, typography(uppercase), coloring (font, bg), spacing (mt to all except 1child)
<-pake dari css tapi bikin lewat tailwind


## Responsive Design
- 5 breakpoints  sm, md, lg, xl, 2xl (responsive varieance) can use to any utilities in tw
- using min-width media queries
- use it as prefix before the utilities (ex: sm:bg-yellow)
- flex and grid
-

## Hover, focus, and other states
- ex_ hover:bg-white-700,focus,active
- active in not active, activate it from tw.config -> variant (hover, focus, active dll.) -> backgroundColor: ["active"], enable overriden list of variant the enable by default. so put in on -> extend:{}. because is just being enable for common thing, if it doesnt work its may need tobe enabled in config


## Composing Utilities with @apply rekomended to use it on common component that have high reuseablity 
- digunakan untuk membuat suatu class custom dengan mengunakan utlities dari tw, dituliskan di tailwind.css sebelum utlities atau tempant lain yang diperlukan karena class akan diproriatas kan berdasasrkan layer
- atau menambahkan layer baru dengan "@layer base/component/utylities"
- .btn{ @apply bg-blue-500} -> generated to conventional class


## extracting reusable components
- extraction on markup level using react jsx
- make component

## costumizing your design
- tw.config -> theme (color, font size, spacing scale )  
- npx tailwindcss init tailwind-full.config.js --full untuk melihat semua config default dari tw
- untuk menambahakan constume style bisa tambahakna ke theme: {extend:{ color:{ brand: "#fff", "brand-light":"#ronrg"}}}
- or use object theme color -> brand:{ DEFAULT:"#fff" ,light: "#fjn"} 
- font costumize: embed font from google link tag > theme -> extend -> fontFamily: {newFont:"Poppins, san-serif}

## optimizing for production
menambahkan theme baru akan menamabahkan semua kemungkinana utilitas class baru di tw.css, tw akan mengenereate banyak sekali class yang dapat memberatkan proses produksi
- add sctipt -> build : vite buld, npm run build - tailwind not purging unsused style
- purgeCss as solution
	di tw.config -> purge -> tambahakan file path  yang harus di scan oleh purge
- purge melakukan scanningg dengwn mencqri class sebai string

=tw 2.1:
Juat-in-time compiler
=ARBITRARY VALUE `
=important !

=2.2 newcvariant pseudoclass 

=3.0
JIT-- just-in-time
print:hidden
snap scroll
scrool smooth, scroll-mt-00
multi column layout, column-x
form default brand. in form, accennt-color, file:bg-x
detail tag, summart, ~div p. use new open variant, open:
fancy underline style, decoration-color
arbitary property, <img class:[clip-path:circle(70%_at_20%_30%)] >
play cdn access


# Referensi