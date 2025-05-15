<script>
  export let year = '';
</script>

<style>
  * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: inherit;
  }

  .content-container {
      position: relative;
      width: 100%;
      margin-bottom: 20px;
      .text-with-line {
          top: 10px;
          position: inherit;
          font-style: normal;
          font-family: Inter;
          font-weight: 400;
          color: #000957;
          margin-right: 16px;
          padding-left: 64px;
      }

      .text-with-line::before {
          content: '';
          position: absolute;
          left: 29px;
          top: 0;
          bottom: 0;
          width: 4px;
          background-color: #000957;
      }
      .circle-with-text {
          width: 100%;
          position: inherit;
          display: inline-flex;
          align-items: center;
          .circle {
              position: inherit;
              width: 1em;
              height: 1em;
              border-radius: 50%;
              border: 3px solid #000957;
              font-size: 64px;
              margin-right: 20px;
          }

          .year {
              position: relative;
              font-family: Inter;
              font-style: normal;
              font-weight: 700;
              color: #344CB7;
              font-size: 53px;
          }
      }
  }
</style>

<div class="content-container">
  <div class="circle-with-text">
    <div class="circle"></div>
    <div class="year">{year}</div>
  </div>
  <div class="text-with-line">
    <slot></slot>
  </div>
</div>
