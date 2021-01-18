<template>
  <div>
    <p>Transaction Form (computed)</p>
    <div name="send-div">
      <div v-if="!isLockedReceiveCur">
        <b @click="isLockedReceiveCur = false">Send:</b>
        <input
          type="number"
          :disabled="validate ? '' : disabled"
          :min="fee"
          step="0.01"
          placeholder="enter send amount"
          v-model="send_cur"
          @click="isLockedReceiveCur = false"
          @select="isLockedReceiveCur = false"
        />
      </div>
      <div v-else>
        <span @click="isLockedReceiveCur = false">c-Send:</span>
        <input
          type="number"
          :disabled="validate ? '' : disabled"
          :min="fee"
          step="0.01"
          placeholder="enter send amount"
          v-model="send_cur_computed"
          @click="isLockedReceiveCur = false"
          @select="isLockedReceiveCur = false"
        />
      </div>
    </div>
    <div name="receive-div">
      <div v-if="isLockedReceiveCur">
        <b @click="isLockedReceiveCur = true">Receive:</b>
        <input
          type="number"
          :disabled="validate ? '' : disabled"
          step=".01"
          placeholder="enter receive amount"
          v-model="receive_cur"
          @click="isLockedReceiveCur = true"
          @select="isLockedReceiveCur = true"
        />
      </div>
      <div v-else>
        <span @click="isLockedReceiveCur = true">c-Receive:</span>
        <input
          type="number"
          :disabled="validate ? '' : disabled"
          step=".01"
          placeholder="enter receive amount"
          v-model="receive_cur_computed"
          @click="isLockedReceiveCur = true"
          @select="isLockedReceiveCur = true"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isLockedReceiveCur: false,
    };
  },
};
</script>

<style>
</style>