Download Link: https://assignmentchef.com/product/solved-ece-325-assignment-3-exception-handling
<br>
<table width="661">

 <tbody>

  <tr>

   <td width="661"></td>

  </tr>

 </tbody>

</table>

The exceptions should propagate the error to the main program which prints the diagnostics of the error. You must handle these errors using Java exceptions and the message should be printed by an exception handler in a catch clause.

These will be the exception test cases:

1 + (2 * 3;                       // syntax error: ‘)’ expected (let x 5) + x;                    // syntax error: ‘=’ expected

(let x = 5) (let y = 6);          // syntax error: operator expected

(let x = 5 let y = 6);            // syntax error: ‘)’ expected

(ler x = 5) ^ (let y = 6);        // runtime error: ‘ler’ undefined (let x = 5) + y;                  // runtime error: ‘y’ undefined

<h1>A Working Procedure Example</h1>

a

<table width="661">

 <tbody>

  <tr>

   <td rowspan="11" width="18"> </td>

   <td width="25"> </td>

   <td width="359">Expression</td>

   <td width="149">Stack</td>

   <td width="89">Pop &amp; Return</td>

   <td width="21">H</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td width="25">1</td>

   <td width="359">1 +</td>

   <td width="149">


    <table width="29">

     <tbody>

      <tr>

       <td width="29">| 1 +|</td>

      </tr>

     </tbody>

    </table></td>

   <td width="89">/</td>

   <td width="21">&lt;</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td rowspan="2" width="25">2</td>

   <td rowspan="2" width="359">1 + (let x = 1</td>

   <td rowspan="2" width="149">


    <table width="57">

     <tbody>

      <tr>

       <td colspan="2" width="57">| let x = 1|</td>

      </tr>

      <tr>

       <td width="29">| 1 +|</td>

       <td width="28"> </td>

      </tr>

     </tbody>

    </table></td>

   <td rowspan="2" width="89">/</td>

   <td rowspan="2" width="21">x</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td width="25">3</td>

   <td width="359">1 + (let x = 1)</td>

   <td width="149">


    <table width="39">

     <tbody>

      <tr>

       <td width="39">| 1 + 1|</td>

      </tr>

     </tbody>

    </table></td>

   <td width="89">1(returned from“let x = 1”)</td>

   <td width="21">x</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td rowspan="2" width="25">4</td>

   <td rowspan="2" width="359">1 + (let x = 1) + (let y = 2) + (1 + x * (1 + y</td>

   <td rowspan="2" width="149">


    <table width="39">

     <tbody>

      <tr>

       <td width="39">| 1 + y|</td>

       <td colspan="2" width="33"> </td>

      </tr>

      <tr>

       <td colspan="2" width="48">| 1 + x *|</td>

       <td width="23"> </td>

      </tr>

      <tr>

       <td colspan="3" width="71">| 1 + 1 + 2 + |</td>

      </tr>

      <tr>

       <td width="23"></td>

       <td width="5"></td>

       <td width="11"></td>

      </tr>

     </tbody>

    </table></td>

   <td rowspan="2" width="89">/(“let y = 2” has already returned 2)</td>

   <td rowspan="2" width="21">x y</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td width="25">5</td>

   <td width="359">1 + (let x = 1) + (let y = 2) + (1 + x * (1 + y)</td>

   <td width="149">


    <table width="57">

     <tbody>

      <tr>

       <td width="57">| 1 + x * 3|</td>

       <td width="9"> </td>

      </tr>

      <tr>

       <td colspan="2" width="67">| 1 + 1 + 2 +|</td>

      </tr>

     </tbody>

    </table></td>

   <td width="89">3(returned from“1 + y”)</td>

   <td width="21">x y</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td rowspan="2" width="25">6</td>

   <td rowspan="2" width="359">1 + (let x = 1) + (let y = 2) + (1 + x * (1 + y)) – (let x = y</td>

   <td rowspan="2" width="149">


    <table width="57">

     <tbody>

      <tr>

       <td width="57">| let x = y|</td>

       <td width="33"> </td>

      </tr>

      <tr>

       <td colspan="2" width="90">| 1 + 1 + 2 + 4 – |</td>

      </tr>

     </tbody>

    </table></td>

   <td rowspan="2" width="89">/(“1 + x * 3” has already returned 4)</td>

   <td rowspan="2" width="21">x y</td>

   <td width="0"></td>

  </tr>

  <tr>

   <td width="25">7</td>

   <td width="359">1 + (let x = 1) + (let y = 2) + (1 + x * (1 + y)) – (let x = y) – x</td>

   <td width="149">


    <table width="118">

     <tbody>

      <tr>

       <td width="118">| 1 + 1 + 2 + 4 – 2 – 2 |</td>

      </tr>

     </tbody>

    </table></td>

   <td width="89">/(“let x = y” has already returned 2)</td>

   <td width="21">x y</td>

   <td width="0"></td>

  </tr>

 </tbody>

</table>

Em

=

=

=

=

=

=

=

=

=

=

<table width="661">

 <tbody>

  <tr>

   <td width="18"> </td>

   <td width="25">8</td>

   <td width="359">1 + (let x = 1) + (let y = 2) + (1 + x * (1 + y)) – (let x = y) – x;</td>

   <td width="149">&lt;Empty&gt;</td>

   <td width="89">4</td>

   <td width="21">x y</td>

  </tr>

 </tbody>

</table>

=