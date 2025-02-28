<script lang="ts">
  let dateValue = $state("00:00 am");
  let clockValue = $state("00:00 am");

  setInterval(() => {
    const date = new Date();

    dateValue = date.toLocaleDateString("en-UK", { weekday: "short", day: "numeric", month: "short", year: "numeric" });
    clockValue = date.toLocaleTimeString("en-US").toLowerCase();
  }, 10);
</script>

<div class="absolute top-4 left-4">
  <p class="font-medium">{dateValue}</p>
  <p class="text-overlay">{clockValue}</p>
</div>