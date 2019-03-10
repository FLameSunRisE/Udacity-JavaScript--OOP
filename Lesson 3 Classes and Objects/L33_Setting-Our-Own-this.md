### call\(\) {#call-}

    function multiply(n1, n2) {
      return n1 * n2;
    }

    multiply(3, 4);
    // 12
    multiply.call(window, 3, 4);
    // 12


    const mockingbird = {
      title: 'To Kill a Mockingbird',
      describe: function () {
        console.log(`${this.title} is a classic novel`);
      }
    };

    mockingbird.describe();
    // 'To Kill a Mockingbird is a classic novel'



