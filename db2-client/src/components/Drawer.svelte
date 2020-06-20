<script>
  import Drawer, {
    AppContent,
    Content,
    Header,
    Title,
    Subtitle,
    Scrim,
  } from "@smui/drawer";
  import Button, { Label } from "@smui/button";
  import List, { Item, Text, Graphic, Separator, Subheader } from "@smui/list";
  import H6 from "@smui/common/H6.svelte";
  import Nav from "./Nav.svelte";

  let myDrawer;
  let myDrawerOpen = true;
  let active = "home";

  function setActive(value) {
    active = value;
  }
</script>

<div class="drawer-container">
  <Drawer>
    <Header>
      <Title>Цифровой прорыв 2</Title>
      <Subtitle>Я ❤️ ДГТУ</Subtitle>
    </Header>
    <Content>
      <List>
        <Item
          href="javascript:void(0)"
          on:click="{() => setActive('home')}"
          activated="{active === 'home'}"
        >
          <Graphic class="material-icons" aria-hidden="true" />
          <Text>Главная</Text>
        </Item>
      </List>
    </Content>
  </Drawer>

  <Scrim />

  <AppContent class="app-content">
    <nav class="navbar">
      <Nav segment="{active}" />
    </nav>
    <main class="main-content">
      <slot />
    </main>
  </AppContent>

</div>

<style>
  .drawer-container {
    position: relative;
    display: flex;
    border: 1px solid rgba(0, 0, 0, 0.1);
    overflow: hidden;
    z-index: 0;
    height: 100%;
  }
  * :global(.mdc-drawer--modal, .mdc-drawer-scrim) {
    /* This is not needed for a page-wide modal. */
    position: absolute;
  }
  * :global(.app-content) {
    flex: auto;
    position: relative;
    flex-grow: 1;
  }
  .navbar {
    position: sticky;
  }
  .main-content {
    overflow: auto;
    padding: 16px;
    height: 100%;
    box-sizing: border-box;
  }
</style>
