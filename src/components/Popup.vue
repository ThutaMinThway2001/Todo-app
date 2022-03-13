<template>
    <v-dialog
        max-width="600"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            color="primary"
            v-bind="attrs"
            v-on="on"
          >Add Project</v-btn>
        </template>
        <template>
          <v-card>
            <v-card-title>
                <h2>Add a New Project</h2>
            </v-card-title>
            </v-card>
        </template>
      </v-dialog>
</template>

<script>
export default {

}
</script>

<style>

</style>