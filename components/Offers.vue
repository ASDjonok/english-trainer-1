<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-2">
        <span>
          Aniroosh shop
        </span>
      </div>

      <div class="col-md-8">
        <ul class="nav">
          <li class="nav-item">
            <a class="nav-link active" href="#">Для вас</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Пошук</a>
          </li>
          <li class="nav-item">
            <a class="nav-link disabled" href="#">Лайки</a>
          </li>
        </ul>
      </div>
      <div class="col-md-2">
        <span>
          $ | ENG
        </span>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12">
        <span>
          Для вас
        </span>
        <button type="button" class="btn btn-success">
          приховати фільтр
        </button>
        <b-dropdown id="dropdown-1" text="Dropdown Button" class="m-md-2">
          <b-dropdown-item>First Action</b-dropdown-item>
          <b-dropdown-item>Second Action</b-dropdown-item>
          <b-dropdown-item>Third Action</b-dropdown-item>
          <b-dropdown-divider></b-dropdown-divider>
          <b-dropdown-item active>Active action</b-dropdown-item>
          <b-dropdown-item disabled>Disabled action</b-dropdown-item>
        </b-dropdown>

      </div>
    </div>
    <div class="row">
      <div class="col-md-2">
        <h3>
          h3. Lorem ipsum dolor sit amet.
        </h3>
        <div class="dropdown">

          <button class="btn btn-primary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown">
            Action
          </button>
          <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
            <a class="dropdown-item disabled" href="#">Action</a> <a class="dropdown-item" href="#">Another action</a> <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </div>
        <div class="dropdown">

          <button class="btn btn-primary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown">
            Action
          </button>
          <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
            <a class="dropdown-item disabled" href="#">Action</a> <a class="dropdown-item" href="#">Another action</a> <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </div>
      </div>
      <div class="col-md-10">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Offers",
  data() {
    return {
      hello: 42,
    }
  },

}
</script>

<style scoped>

</style>
