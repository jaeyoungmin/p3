<template>
  <div class="card-container">
    <div class="card-body">
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Itaque eius,
        ipsum deleniti ut quos labore a, quibusdam nemo similique molestiae odit
        id quam. Voluptatem inventore illum enim animi. Quas, minima.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
};
</script>

<style lang="scss" scoped>
.card-container {
  background: #fff;
  box-shadow: 0px 2px 10px rgba(0, 0, 0, 0.15);
  width: 100%;
  height: 100%;
  cursor: pointer;
  margin-bottom: 2rem;
  .card-body {
    padding: 1rem 2rem;
    p {
      font-size: 1.5rem;
    }
  }
}
</style>
