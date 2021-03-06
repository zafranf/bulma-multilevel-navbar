# Bulma Multilevel Navbar
[Demo](https://zafranf.github.io/bulma-multilevel-navbar.html)

## HTML
```
<div id="menubar" class="container is-fluid">
  <nav class="navbar">
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <img src="https://bulma.io/images/bulma-logo.png" alt="Bulma: a modern CSS framework based on Flexbox" width="112" height="28">
      </a>
      <div class="navbar-burger burger" data-target="navbar-main-menu">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
    <div id="navbar-main-menu" class="navbar-menu">
      <div class="navbar-start">
        <a class="navbar-item" href="#">Example</a>
        <div class="navbar-item has-dropdown is-hoverable">
          <div class="navbar-link">Multilevel</div>
          <div class="navbar-dropdown">
            <a class="navbar-item" href="#">Link 1</a>
            <a class="navbar-item" href="#">Link 2</a>
          </div>
        </div>
        <div class="navbar-item has-dropdown is-hoverable">
          <div class="navbar-link">Navbar</div>
          <div class="navbar-dropdown">
            <a class="navbar-item" href="#">Link 3</a>
            <div class="navbar-item submenu has-dropdown is-hoverable">
              <div class="navbar-link submenu">Link 4</div>
              <div class="navbar-dropdown submenu">
                <a class="navbar-item" href="#">Link 4-1</a>
                <a class="navbar-item" href="#">Link 4-2</a>
              </div>
            </div>
            <a class="navbar-item" href="#">Link 5</a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</div>
```

## CSS
```
.navbar-item.submenu .navbar-link.submenu {
  background: transparent;
  padding-left: 0;
}

@media screen and (min-width: 1008px) {
  #menubar {
    border-bottom: 1px solid #ccc;
    margin: 0;
    margin-bottom: 20px;
  }
  #menubar .navbar {
    padding: 0 20px;
  }
  .navbar-dropdown {
    min-width: 160px;
  }
  .navbar-link {
    cursor: pointer;
  }
  .navbar-item.submenu .navbar-link.submenu {
    padding-top: 0;
    padding-bottom: 0;
    display: block;
    width: 100%;
  }
  .navbar-item.submenu:hover {
    background: whitesmoke;
  }
  .navbar-item.submenu .navbar-link.submenu:after {
    -webkit-transform: rotate(-135deg);
    transform: rotate(-135deg);
    left: 90%;
    top: 58%;
  }
  .navbar-item.submenu .navbar-dropdown.submenu {
    display: none;
    position: absolute;
    left: 100%;
    top: 0;
  }
  .navbar-item.submenu.is-active .navbar-dropdown.submenu,
  .navbar-item.submenu.is-hoverable:hover>.navbar-dropdown.submenu {
    display: block;
  }
}
```

## JS
```
document.addEventListener('DOMContentLoaded', function() {

  // Get all "navbar-burger" elements
  var $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0);

  // Check if there are any navbar burgers
  if ($navbarBurgers.length > 0) {

    // Add a click event on each of them
    $navbarBurgers.forEach(function($el) {
      $el.addEventListener('click', function() {

        // Get the target from the "data-target" attribute
        var target = $el.dataset.target;
        var $target = document.getElementById(target);

        // Toggle the class on both the "navbar-burger" and the "navbar-menu"
        $el.classList.toggle('is-active');
        $target.classList.toggle('is-active');

      });
    });
  }
});
```