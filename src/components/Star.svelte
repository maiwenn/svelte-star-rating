<script>
  export let id, readOnly, fillPercentage, starConfig;
</script>

<svg xmlns="http://www.w3.org/2000/svg" width="{starConfig.size}" viewBox="0 0 492.8 469.9" height="{starConfig.size}" >
  {#if fillPercentage < 1 && fillPercentage > 0}
    <defs>
      <linearGradient id="linear-gradient-{id}" x1="0%" y1="0%" x2="100%" y2="0%">
        <stop offset="0%" style="stop-color:{starConfig.fillColor};stop-opacity:1" />
        <stop offset="{fillPercentage * 100}%" style="stop-color:{starConfig.fillColor};stop-opacity:1"/>
        <stop offset="{fillPercentage * 100}%" style="stop-color:{"white"};stop-opacity:1" />
      </linearGradient>
    </defs>
  {/if}
  <path
    opacity="{readOnly ? 1 : 1}"
    stroke={starConfig.strokeColor}
    fill={fillPercentage === 1 ? starConfig.fillColor : fillPercentage === 0 ? "white" : `url(#linear-gradient-${id})`}
    d="M245.9,0c-4.7,0.2-8.7,3.3-10.2,7.8L183,171.2l-171.7-0.3c-4.9,0-9.2,3.1-10.7,7.7c-1.5,4.6,0.1,9.7,4.1,12.5
		l139.2,100.7L90.4,455.2l0,0c-1.5,4.6,0.1,9.7,4.1,12.5c3.9,2.9,9.3,2.9,13.2,0l138.8-101.3l138.8,101.3v0c3.9,2.9,9.2,2.9,13.2,0
		c3.9-2.9,5.6-7.9,4.1-12.5L349,291.9l139.2-100.7l0,0c3.9-2.9,5.6-7.9,4.1-12.5c-1.5-4.6-5.8-7.8-10.7-7.7l-171.7,0.3L257,7.8
		C255.5,3,250.9-0.2,245.9,0L245.9,0z"
  />
</svg>
