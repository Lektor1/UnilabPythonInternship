
# css

**cascading style sheets** ( CSS ) აღწერს თუ როგორ გამოჩნდება HTML ელემენტები ვებ გვერდზე.
CSS შეუძლია რამოდენიმე სხვადასხვა გვერდზე განლაგებულ ელემენტებზე იქონიოს გავლენა. სტილის დაწერა შეგვიძლია თვითონ html დოკუმენტში, კონკრეტულ html ელემენტზე და დაკავშირებულ ფაილში, მაგ.: `style.css`

## სტილის უპირატესობის იერარქია

- inline style - გულისხმობს კონკრეტულ html ელემენტზე გაწერილ სტილს. ამისთვის გამოიყენება style ატრიბუტი. ამგვარი სტილი უპირატესია ყველა სხვა ფორმით გაწერილ სტილზე.

```html
<p style="color: red">This is a paragraph.</p>
```

- internal style - გულისხმობს html დოკუმენტში გაწერილ სტილს. ამისთვის `<head> </head>` ბლოკში გამოიყენება `<style> </style>`. ამგვარი სტილი არაა უპირატესი inline სტილზე.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>

    <style>
      h1 {
        color: blue;
      }
    </style>
  </head>

  <body>
    <h1>This is a heading</h1>
  </body>
</html>
```

- external style - გულისხმობს დამოუკიდებელ css დოკუმენტში გაწერილ სტილს. ამისთვის html დოკუმენტს `<head> </head>` ბლოკში უნდა დავუკავშიროთ css დოკუმენტი. ამგვარი სტილი არაა უპირატესი inline სტილზე.

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="./style.css" />
    <title>Document</title>
  </head>

  <body>
    <h1>This is a heading</h1>
  </body>
</html>
```

ატრიბუტი `rel` აღნიშნავს ბმული ფაილის ტიპს/როლს _html_ ფაილისთვის, ხოლო
`href`-ში თავსდება იმ ფაილის მისამართი სადაც სტაილშიტია მოთავსებული.

## css სტრუქტურა

![ანატომია](https://mdn.mozillademos.org/files/9461/css-declaration-small.png)

## class და id

ყოველ HTML ელემენტს აქვს შესაძლებლობა მიენიჭოს class ან id ატრიბუტი. ამ ატრიბუტების დახმარებით შეგვიძლია მივწვდეთ სასურველ ელემენტებს.

**class**-ის გამოყენებით შეგვიძლია გავაერთიანოთ სხვადასხვა (თუნდაც არაერთგვაროვანი ტიპის) html
ელემენტი და მივანიჭოთ მათ საერთო მახასიათებელი.

**id**-ის მეშვეობით შეგვიძლია ინდივიდუალურად ავირჩიოთ html ელემენტი რომელზეც გვსურს რეაგირება.
შესაბამისად ყოველ ელემენტს უნდა ჰქონდეს უნიკალური ინდივიდუალური id მნიშვნელობა.

## css სინტაქსი:

`#` - გამოიყენება id-ის გამოსაძახებლად
`.` - გამოიყენება class-ის გამოსაძახებლად

მაგალითად:

```css
.class {
  background: maroon;
}

#id {
  background: green;
}
```

# [Bootstrap4](https://getbootstrap.com/)

### [შესავალი](https://getbootstrap.com/docs/4.5/getting-started/introduction/) | [მაგალითები](https://getbootstrap.com/docs/4.5/examples/) | [დოკუმენტაცია](https://getbootstrap.com/docs/4.5/layout/overview/)

Boostrap არის მსოფლიოში ერთ-ერთი ყველაზე პოპულარული ფრონტ-ენდ დეველოპმენტ იარაღების ნაკრები. იგი შექმნეს twitter -ის დეველოპერებმა. მას აქვს html ელემენტების და css სტილის მზა შაბლონები.

## როგორ გამოვიყენოთ Bootstrap

არსებობს Bootstrap-ის პროექტში ჩაშენების რამოდენიმე გზა.

- თქვენ შეგიძლიათ ინდივიდუალურად [გადმოწეროთ Bootstrat](https://getbootstrap.com/docs/4.5/getting-started/download/)
  სორს კოდთან და კომპონენტებთან ერთად.
- დააყენოთ რომელიმე სასურველი Package Manager-ის მეშვეობით (npm, yarn, RubyGems, NuGet, Composer).
- შემოიტანოთ შესაბამისი ბმულები html ფაილში, [BootstrapCDN](https://www.bootstrapcdn.com/) ის მეშვეობით.

### cdn -ით დაყენება

```html
<!-- in head section -->
<!-- Chapter3_CSS only -->
<link
  rel="stylesheet"
  href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css"
  integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z"
  crossorigin="anonymous"
/>

<!-- at the end of the body section -->
<!-- JS, Popper.js, and jQuery -->
<script
  src="https://code.jquery.com/jquery-3.5.1.slim.min.js"
  integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj"
  crossorigin="anonymous"
></script>
<script
  src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js"
  integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN"
  crossorigin="anonymous"
></script>
<script
  src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"
  integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV"
  crossorigin="anonymous"
></script>
```

## [bootstrap სტილი](https://getbootstrap.com/docs/4.5/layout/overview/)

bootstrap სტილის გამოყენებისთვის სასურველ html ელემენტს უნდა მივანიჭოთ bootstrap class-ი.

```html
<button type="button" class="btn btn-primary">Primary</button>
```

## [კომპონენტები](https://getbootstrap.com/docs/4.5/components/)

**კომპონენტი** Bootstrap-ში წინასწარ გამზადებული ვებ-გვერდის შაბლონია.

### [navbar](https://getbootstrap.com/docs/4.5/components/navbar/)

თანამედროვე ვებ გვერდის მნიშვნელოვან ატრიბუტს წარმოადგენს navbar - სანავიგაციო ზოლი. ბუტსტრეპის ნავბარები არის რესპონსივ ელემენტები რაც ნიშნავს რომ ის ავტომატურად იცვლის ზომას ან ფორმას
ეკრანის ტიპისა და გაფართოების გათვალისწინებით.

```html
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Navbar</a>
  <button
    class="navbar-toggler"
    type="button"
    data-toggle="collapse"
    data-target="#navbarNavAltMarkup"
    aria-controls="navbarNavAltMarkup"
    aria-expanded="false"
    aria-label="Toggle navigation"
  >
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
    <div class="navbar-nav">
      <a class="nav-link active" href="#"
        >Home <span class="sr-only">(current)</span></a
      >
      <a class="nav-link" href="#">Features</a>
      <a class="nav-link" href="#">Pricing</a>
      <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true"
        >Disabled</a
      >
    </div>
  </div>
</nav>
```

## დამატებითი რესურსები

1. [HTML-ის დოკუმენტაცია](https://developer.mozilla.org/en-US/docs/Web/HTML)
2. [css -ის დოკუმენტაცია](https://developer.mozilla.org/en-US/docs/Web/css)
3. [Bootstrap -ის დოკუმენტაცია](https://getbootstrap.com/docs/5.0/getting-started/introduction/)
