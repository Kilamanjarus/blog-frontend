<template>
  <div class="container">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
          aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="http://localhost:8080/">Home</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/posts">Posts</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/posts/new">Create Post</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="/about">About</a>
            </li>
            <div class="dropdown">
              <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton2"
                data-bs-toggle="dropdown" aria-expanded="false">
                Profile
              </button>
              <ul class="dropdown-menu dropdown-menu-dark" aria-labelledby="dropdownMenuButton2">
                <li><a class="dropdown-item active" href="/signup">Signup</a></li>
                <li><a class="dropdown-item active" href="/login">Login</a></li>
                <li><a class="dropdown-item" href="#">Profile</a></li>
              </ul>
            </div>
          </ul>
        </div>
      </div>
    </nav>
  </div>
  <router-view />
</template>

<style>
#app {
  font-family: Courier New, Courier, Lucida Sans Typewriter, Lucida Typewriter, monospace;
  background-image: url("https://www.toptal.com/designers/subtlepatterns/uploads/more-leaves-on-green.png");
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
