# dithering-with-css
SVG filter to create dithering effect for CSS


```
  <svg>
      <filter id="dither" color-interpolation-filters="sRGB" x="0" y="0" width="100%" height="100%">

        <!-- 8 x 8 dither pattern -->
        <feImage width="8px" height="8px" result="d" xlink:href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAICAYAAADED76LAAAA+UlEQVR42gXBERTCUABA0X/OYDAYDAZBEAyCIBgMgiAIgiAYBINgEAwGgyAIBsFgMAiCIAiCIAgGQTAYDAaDIAiCwWDwulcIIXg8HgwGA36/H4qi8Hq9sCyLtm0Rm82G0WjE5XJhvV4ThiHT6ZT7/U4QBIhut0tVVaiqSpZl9Pt9vt8vnU6HsiwRh8OB5XLJfr9nNptxPp9xXZckSbBtGyHLMs/nE9M0aZoGSZJI05ThcEhd14jdbsdkMuF2u+H7PtvtlvF4zPV6xfM8hGEYfD4fdF2nKAp6vR7v9xtN08jzHHE6nVitVsRxzGKx4Hg84jgOURQxn8/5A7oKnYRU4EpfAAAAAElFTkSuQmCC"/>

        <!-- 4 x 4 dither pattern -->
        <!-- <feImage width="4px" height="4px" result="d" xlink:href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAQAAAAECAYAAACp8Z5+AAAASElEQVR42gXBgQAAIAxFwW8QwhBCCCGEIYQQQgghhBBCCEMYwutOkphzYmbsvdG9l9YaEYG7o1or5xxKKay1UGYyxuC9R++dD7yGJkTj6F0HAAAAAElFTkSuQmCC"/> -->

        <!-- 2 x 2 dither pattern -->
        <!-- <feImage width="2px" height="2px" result="d" xlink:href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAIAAAACCAYAAABytg0kAAAAG0lEQVR42mNgYGD4X19f/59h//79/+3t7f8DAEGyCHSQnFc+AAAAAElFTkSuQmCC"/> -->

        <feTile in="d" result="tiled"/>

        <feComposite operator="arithmetic" k1="0" k2="1" k3="1" k4="-0.5" in2="tiled" in="SourceGraphic" result="blend"/>

        <feComponentTransfer in="blend">
          <feFuncR type="discrete" tableValues="0 1" />
          <feFuncG type="discrete" tableValues="0 1" />
          <feFuncB type="discrete" tableValues="0 1" />
          <feFuncA type="discrete" tableValues="0 1" />
        </feComponentTransfer>
      </filter>
    </svg>
```


## refering to the filter in CSS ##
```
img {
  filter: url(#dither);
}
```


