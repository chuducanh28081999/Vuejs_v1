<template>
  <div>
    <b-sidebar id="sidebar-no-header" aria-labelledby="sidebar-no-header-title" no-header shadow>
      <template #default="{ hide }">
        <div class="p-4">
          <h3 id="sidebar-no-header-title">Dash Board</h3>
          <template>
            <b-icon icon="person" scale="2"></b-icon>
          </template>
          <b-button variant="primary" block @click="hide">Close Sidebar</b-button>
        </div>
      </template>
    </b-sidebar>
  </div>
</template>
