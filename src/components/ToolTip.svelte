<script context="module">
  import HelpStrings from "../data/help";

  export const getHelpMessage = (key) => {
    if (HelpStrings[key]) {
      return `${HelpStrings[key].text} <br><a href="${HelpStrings[key].more_info}"> Learn more </a>`;
    }
    return "Specific information not found";
  };
</script>

<script>
  import tippy from "sveltejs-tippy";
  export let props = {
    content: "<span class='tooltip'>Tooltip Info</span>",
    allowHTML: true,
    placement: "top",
  };
</script>

<style>
  .main {
    text-align: center;
  }
  :global(.tooltip) {
    font-size: 1.2rem;
    text-transform: uppercase;
  }
</style>

<div class="main">
  <section use:tippy={props}>
    <slot />
  </section>
</div>
