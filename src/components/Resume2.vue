<template lang="html">
  <div class="resume2">
    <article>

      <header>
        <!-- force flexbox to keep name on a single line -->
        <h1>Abe&nbsp;Lincoln</h1>
        <p>
          1441 Monument Avenue<br/> Springfield, IL 62702<br/>
          <a href="tel:1-217-782-2717">217.782.2717</a>
          <a href="http://www.alplm.org">website</a>
          <a href="http://www.alplm.org">website</a>

        </p>
      </header>

      <div class="one-col">
        <section>
          <h2>EXPERIENCE</h2>

          <h3><strong>16th U.S. PRESIDENT</strong> Washington, DC 1861-1865</h3>
          <ul>
            <p>Served as the first Republican Party president and built the Republican Party into a powerful national organization.
              Defended and preserved the unity of the United States by defeating the secessionist Confederacy in the Civil War, and instituted a formal Reconstruction Plan to reunite the nation after the war.
              Supervised all aspects of the war effort and selected top generals (including Ulysses S. Grant) to lead military campaigns.
              Issued the Emancipation Proclamation in 1863, freeing slaves within the Confederacy. Endorsed the 13th Amendment to the Constitution, which totally abolished slavery.
              Delivered the Gettysburg Address, the most famous speech in American history.</p>
              <li>Signed landmark legislation, including the National Banking Act, legislation that protected American industry, and a bill that chartered the first transcontinental railroad.</li>
              <li>Supported the Federal Homestead Law (1862), which allowed poor people in the east to acquire land in the west.</li>
            </ul>

            <h3><strong>ILLINOIS STATE REPRESENTATIVE</strong> Vandalia - Springfield, IL 1834-1842</h3>
            <ul>
              <li>Led the Long Nine group of seven legislators and two senators in moving the state capital from Vandalia to Springfield.</li>
              <li>Helped pass a bill to build better roads and construct a system of canals and railroads making Illinois a more progressive and accessible state.
              </li>
            </ul>

            <h3><strong>ATTORNEY AT LAW</strong> Vandalia - Springfield, IL 1836-1861</h3>
            <ul>
              <li>Prepared cases for federal courts, the Illinois Supreme Court and the state’s Eighth Judicial Circuit. Admitted to practice in United States Circuit Court in 1839.</li>
              <li>Joined the Republican Party in 1856 and gained national attention by challenging Stephen A. Douglas to a series of debates in 1858.</li>
            </ul>

            <h3><strong>POSTMASTER</strong> New Salem, IL 1833-1836</h3>
            <ul>
              <li>Worked diligently to serve and please customers.</li>
              <li>Routinely walked several miles to deliver mail when I know that someone is waiting for an important letter.</li>
            </ul>
          </section>

          <div class="two-col">
            <section>
              <h2>EDUCATION</h2>
              <ol>
                <li>Honorary Doctor of Laws <strong>Princeton University <em>1864</em></strong></li>
                <li>Honorary Degree <strong>Columbia <em>1861</em></strong></li>
                <li>Knox College's First Honorary Doctorate <strong>Knox College <em>1860</em></strong></li>
              </ol>
            </section>
            <section>
              <h2>SKILLS</h2>
              <ul>
                <li>Accomplished storyteller</li>
                <li>Excellent writing ability</li>
                <li>Works well with people</li>
                <li>Moderate abolitionist</li>
                <li>Only US president to own a patent, granted in 1849 for device to lift boats over shoals</li>
              </ul>
            </section>
          </div>
        </div>
      </article>
    </div>
  </template>

  <script>
  export default {
    name: 'resume2',
  }
  </script>

  <style lang="scss">
  .resume2 {

    @import url(https://fonts.googleapis.com/css?family=Raleway:400,300,600);

    * {
      box-model: border-box;
    }

    article {
      background-color: white;  
    }


    /* simple use of flex-box to create layout from <div> "grouping" tags. The key is to remember that your CSS layout solution has everything to do with the decisions you make in the HTML  */
    article,
    .two-col {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
    }

    article {
      padding: 5%;
    }

    header {
      padding: 0 3%;
      border-right: 1px solid silver;
      margin-right: 3%;
    }

    .two-col section {
      flex: 1;
      /*better than declaring width if you require equal columns*/
    }


    /* example layout mediaquery */
    @media only screen and (max-width: 768px) {
      article,
      .two-col {
        flex-direction: column;
      }
      header {
        border-right: none;
        margin: 0;
        padding: 0;
      }
    }


    /**********
    CSS Type & Design - "The simple stuff"
    ************/

    h1,
    h2,
    h3 {
      font-family: 'Raleway';
      margin-top: 0;
      font-weight: 300;
    }

    h1 {
      font-weight: 300;
      text-transform: uppercase;
    }

    h2 {
      font-size: .9em;
      letter-spacing: .5em;
      font-weight: 600;
      padding: 5px 10px;
      color: #cdcdcd;
      background-color: #ededed;
    }

    h3 {
      padding-right: .5em;
      font-weight: 600;
      font-size: .8em;
      /*  flexbox is handy here too  */
      display: flex;
      justify-content: space-between;
      align-items: center
    }

    h3 strong {
      font-size: 1.5em
    }

    p,
    li {
      font-family: Georgia;
    }

    p {
      text-align: center;
    }

    a {
      font-family: 'Raleway';
      font-weight: 300;
      text-transform: uppercase;
      letter-spacing: .2em;
      /* links can be made into decorative buttons*/
      display: block;
      text-decoration: none;
      background-color: #333;
      color: white;
      margin: 50px 0;
      padding: 20px 0;
      box-shadow: inset 0 0 0 4px white, 0 0 0 1px gray;
      transition: all .5s ease;
    }

    a:hover {
      background: white;
      color: black;
      box-shadow: inset 0 0 0 4px silver, 0 0 0 1px silver;
    }

    ol,
    ul {
      list-style-type: none;
      padding: 0;
      font-size: .85em;
      line-height: 1.5;
    }

    li {
      margin-bottom: 1em;
    }

    .two-col section:first-child h2 {
      margin-right: 2%;
    }

    .two-col ol strong {
      display: block;
    }


    /* example iPhone type design tweaking for single columns */

    @media only screen and (max-width: 768px) {
      /* A fun CSS hack to convert list of skills to comma separated paragraph.   */
      .two-col ul li {display: inline;}
      .two-col ul li:after {content: ","}
      .two-col ul li:last-child:after {content: "."}


      .two-col ol li {
        display: flex;
        justify-content: space-between;
        margin-bottom: .2em;
      }

      .two-col li {
        font-size: .85em;
      }

      h1 {
        text-align: center;
        font-size: 3em;
        margin-bottom: 0;
      }
      h3 {
        display: block;
        text-align: center;
      }
      h3 strong {
        display: block;
        margin-top: .5em;
      }
      a {
        display: inline-block;
        width: 48%;
        margin-top: 24px;
        margin-bottom: 0;
      }
      a:nth-of-type(1) {
        margin-right: 1%;
      }
      a:nth-of-type(2) {
        margin-left: 1%;
      }
      h2 {
        background-color: transparent;
        color: silver;
        font-weight: 300;
        font-size: 2em;
        letter-spacing: 0;
        text-align: center;
        margin-bottom: 0;
      }
    }

  }
  </style>
