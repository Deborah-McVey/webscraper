# Ruby on Replit

This is a template to get you started with Ruby on Replit. It's ready to go so you can just hit run and start coding!

## Running the repl

Simply hit run! You can edit the run command from the `.replit` file.

## Installing packages

To add packages to your repl, we recommend using the Replit packager interface in the left sidebar or using `bundle install` in the shell. Check out the [Bundle docs here](https://bundler.io/guides/getting_started.html).

**Warning: Avoid using `gem install` to add packages.**

Beacuse Ruby repls use [Bundle](https://bundler.io/) under the hood to provide a consistent environment that tracks and installs the exact gems and versions needed, we recommend using `bundle install` instead of `gem install`, which may not work as expected.

## Help

If you need help you might be able to find an answer on our [docs](https://docs.replit.com) page. Feel free to report bugs and give us feedback [here](https://replit.com/support).

Define a class called API and include a class method called get_films_by_year that takes in a year as an argument. We will use year to get a list of films from Wikipedia.

Then we use the HTTParty.get method to make a GET request to the Wikipedia page for the year that we pass in as an argument.

Since we have the unparsed_page, we aren't able to make use of it until we parse it into a nokogiri object.

Targeting elements goes from left to right in the string as you go down the hierarchy. Parent element to child element.

The css method selects the table.wikitable.sortable tr td:nth-child(2) i a element.

table.wikitable.sortable tr td:nth-child(2) i a represents the series of hierarchy levels to get to the table and the elements. It is used to select elements from the document that you requested for. You should inspect the elements on the web page when scraping and find the elements that you want to select based off the selector or class name. Getting to this point takes time and trial and error. Depending on the webpage, it can be difficult to select the elements that you want.

What you are doing here is basically finding the parent element, targeting it by it's CSS and then finding the child element and targeting it.

So you have a table element with classes of wikitable and sortable. This is used to specify the table that you want to select since there's many tables on the page.

As you target the specific table, you then target the tr element since it will include all the rows of the films. Technically, it will also include the header rows. So we have to specify that we want td for table data to remove the header rows.

Then you have a nth-child(2) element right after. This will only allow us to extract the second child element from every td which will include the title of the film that we want. Then you have an i element. Then you have an a element.

This will return an array of nokogiri instances.

In which we can use to iterate and strip the text from the elements.

Then we use the each_with_index method to iterate over the films and print out the films to the terminal.

Nokogiri can be buggy and it can be difficult to use. It is not always accurate. You may have to try different CSS selectors to get the data that you want.