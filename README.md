# bulma-multilevel-navbar
Bulma Multilevel Navbar

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
      <div class="navbar-item  has-dropdown is-hoverable">
        <div class="navbar-link">Multi</div>
        <div class="navbar-dropdown">
          <div class="navbar-item submenu has-dropdown is-hoverable">
            <a class="navbar-link submenu" href="#">Level</a>
            <div class="navbar-dropdown submenu">
              <a class="navbar-item" href="#">Navbar</a>
            </div>
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