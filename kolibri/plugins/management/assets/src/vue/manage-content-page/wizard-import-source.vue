<template>

  <core-modal
    :title="$tr('title')"
    @cancel="cancelImportExportWizard"
  >
    <div class="main">
      <div class="lg-button-wrapper">
        <icon-button class="large-icon-button" :text="$tr('internet')" :showTextBelowIcon="true" @click="showImportNetworkWizard">
          <mat-svg class="icon" category="action" name="language"/>
        </icon-button>
        <icon-button class="large-icon-button" :text="$tr('localDrives')" :showTextBelowIcon="true" @click="showImportLocalWizard">
          <mat-svg class="icon" category="device" name="storage"/>
        </icon-button>
      </div>
      <icon-button
        @click="cancelImportExportWizard"
        :text="$tr('cancel')"/>
    </div>
  </core-modal>

</template>


<script>

  const actions = require('../../actions');

  module.exports = {
    $trNameSpace: 'wizard-import-source',
    $trs: {
      title: 'Please choose a source...',
      internet: 'Internet',
      localDrives: 'Local Drives',
      cancel: 'Cancel',
    },
    components: {
      'core-modal': require('kolibri.coreVue.components.coreModal'),
      'icon-button': require('kolibri.coreVue.components.iconButton'),
    },
    vuex: {
      actions: {
        showImportNetworkWizard: actions.showImportNetworkWizard,
        showImportLocalWizard: actions.showImportLocalWizard,
        cancelImportExportWizard: actions.cancelImportExportWizard,
      },
    },
  };

</script>


<style lang="stylus" scoped>

  @require '~kolibri.styles.definitions'

  .main
    text-align: center
    margin-bottom: 4em 0

  .large-icon-button
    min-width: 150px
    min-height: 120px
    margin: 3px

  .lg-button-wrapper
    margin: 4em 0

  .cancel-btn
    margin-bottom: 2em

  .text-only-buttons
    height: 36px
    padding-right: 2em
    padding-left: 2em
    margin: 1em
    color: $core-text-annotation
    border: 1px $core-text-annotation solid

  .icon
    width: 50px
    height: 50px

</style>
