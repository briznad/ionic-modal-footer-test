<script lang="ts" module>
  import { handleEnterKey } from "@ionic-sveltekit/components";
</script>

<script lang="ts">
  let modalElement: HTMLIonModalElement | undefined;

  function dismissModal(): void {
    modalElement?.dismiss(null, "cancel");
  }
</script>

<ion-card>
  <ion-card-header>
    <ion-card-title>Modal Footer Test</ion-card-title>

    <ion-card-subtitle>Seems okay to me?</ion-card-subtitle>
  </ion-card-header>

  <ion-card-content>
    <ion-button id="open-modal">Open</ion-button>

    <ion-modal trigger="open-modal" bind:this={modalElement}>
      <ion-header>
        <ion-toolbar>
          <ion-buttons slot="start">
            <ion-button
              onclick={dismissModal}
              onkeydown={handleEnterKey(dismissModal)}
              role="button"
              tabindex="0">Cancel</ion-button
            >
          </ion-buttons>
          <ion-title>Welcome</ion-title>
          <ion-buttons slot="end">
            <ion-button
              onclick={dismissModal}
              onkeydown={handleEnterKey(dismissModal)}
              role="button"
              tabindex="0"
              strong={true}>Confirm</ion-button
            >
          </ion-buttons>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <ion-item>
          <ion-input
            label="Enter your name"
            label-placement="stacked"
            type="text"
            placeholder="Your name"
          ></ion-input>
        </ion-item>
      </ion-content>
      <ion-footer>
        <ion-toolbar>
          <ion-title>Footer</ion-title>
        </ion-toolbar>
      </ion-footer>
    </ion-modal>
  </ion-card-content>
</ion-card>

<style></style>
