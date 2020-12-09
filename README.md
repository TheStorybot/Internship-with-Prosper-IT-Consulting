## Live Project

##### Introduction

For the last two weeks in the Tech Academy, I worked with a team of other students/junior developers on a full scale web site for a Theatre company using 
ASP.Net/MVC/EntityFramework/C#.  Working on a large live project in a setting designed to emulate what a 2 week sprint in the life of a software developer would be like, 
was an excellent learing opportunity.  I was able to work out issues with front-end layout, new languages I hadn't worked with, and even complete conversion 
from custom CSS to Bootstrap 4.  I was able to see how good developers work in a team and have discussions daily about where the project was 
and what each individual was currently tasked with.  Throughout the sprint I primarily worked on front-end stories with varying degree of difficulty.

Below are some of the stories are working on during the 2 week sprint.

***

In this snippet I had to make the dropdown bars dynamic to changes in screen size so that it had breakpoints.  
I took the code that was originally written as a table and converted it to a Bootstrap 4 Grid.  I then had to handle some of the spacing between the dropdown filters in large screen format and after breakpoints.
### Before
```
*Modified te code to alter the display of the following section between nav and create new to be centered*
<h2 class="mx-auto mb-3 mt-4 text-center">Part</h2>
<div class="table-responsive">
    <table class="table-borderless mx-auto w-auto">
        <tbody>
            <tr>
                <td class="text-left">Filter By...</td>
            </tr>
            <tr>
                <td>
                    @*The HTML helper creates a form and when the form is submitted it calls the Index() method from PartController.*@
                    @*Had to apply a row to the form and move the col to a div o get the drop downs spaces out and adjusted the margis to pull top and bottm closer*@
                    @using (Html.BeginForm("Index", "Part", FormMethod.Post, new { @id = "partsForm", @class = "row mx-auto mt-n2 mb-n3" }))
                    {
                        // Creates a drop down list referencing the information from ViewData dictionary, which contains 'ProductionsID' key. The value that is selected is submitted onchange.
                        <div class="col-4 px-0">
                            @Html.DropDownList("ProductionsID", (IEnumerable<SelectListItem>)null, "All Productions", new { @class = "text-muted", @onchange = "document.getElementById('partsForm').submit();" })
                        </div>
                        <div class="col-4">
                            @Html.DropDownList("CastMembersID", (IEnumerable<SelectListItem>)null, "All Cast Members", new { @class = "text-muted", @onchange = "document.getElementById('partsForm').submit();" })
                        </div>
                        <div class="col-4 px-0">
                            @Html.DropDownList("Roles", (IEnumerable<SelectListItem>)null, "All Roles", new { @class = "text-muted", @onchange = "document.getElementById('partsForm').submit();" })
                        </div>
                    }
                </td>
            </tr>
            <tr>
                <td class="text-right">@Html.ActionLink("Reset Filters", "ResetFilters")</td>
            </tr>
        </tbody>
    </table>
</div>
```
### After

```
@*Modified the code changing it to bootstrap grid columns*@
<h2 class="mx-auto mb-3 mt-4 text-center">Part</h2>
<div class="container">       
            <div>
                <div class="text-left">Filter By...</div>
                           
                    @*The HTML helper creates a form and when the form is submitted it calls the Index() method from PartController.*@
                    @*Had to apply a row to the form and move the col to a div o get the drop downs spaces out and adjusted the margis to pull top and bottm closer*@
                    @using (Html.BeginForm("Index", "Part", FormMethod.Post, new { @id = "partsForm", @class = "row no-gutters mx-auto mt-n2 mb-n3" }))
                    {
                        // Creates a drop down list referencing the information from ViewData dictionary, which contains 'ProductionsID' key. The value that is selected is submitted onchange.
                        <div class="col-md-4 mb-0">
                            @Html.DropDownList("ProductionsID", (IEnumerable<SelectListItem>)null, "All Productions", new { @class = "text-muted", @onchange = "document.getElementById('partsForm').submit();" })
                        </div>
                        <div class="col-md-4 px-md-1">
                            @Html.DropDownList("CastMembersID", (IEnumerable<SelectListItem>)null, "All Cast Members", new { @class = "text-muted my-md-2 my-0", @onchange = "document.getElementById('partsForm').submit();" })
                        </div>
                        <div class="col-md-4 mt-0">
                            @Html.DropDownList("Roles", (IEnumerable<SelectListItem>)null, "All Roles", new { @class = "text-muted", @onchange = "document.getElementById('partsForm').submit();" })
                        </div>
                    }
                             
                <div class="text-right">@Html.ActionLink("Reset Filters", "ResetFilters") </div>
            </div>
</div>
```

***

In this snippet I transformed the ActionLink into a button from the templates that were available. Originally I used razor syntax in order to achieve it but it did not fit the template format.

```
            <button class="iconBtn" onclick="window.location.href ='@Url.Action("Create", "Awards")'">
                <!-- or buttons can be in their own container-->
                <i class="fa fa-plus-square fa-fw"></i>Create New<!-- This button is a link to a different page -->
            </button>
```

***

# Final Thoughts
The experience was very insightful and lent me the knowledge and confidence to further persue a career in the Software Development/Tech industry.
