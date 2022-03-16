<svelte:options tag="my-tutorial" />

<script>
  export let user;
  $: _user = JSON.parse(user);

  const onButtonClick = () => {
    _user.age += 1;
  };
</script>

<main>
  <h1>Hello {_user.name}!</h1>
  <p>{_user.phone}</p>
  {_user.age}
  {_user.address.prefecture}
  <button on:click={onButtonClick}>Increment age</button>
  <slot />
</main>

<style>
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }
</style>
