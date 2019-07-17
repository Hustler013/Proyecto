# Proyecto
# Load the shiny package
library(shiny)

# Define UI for the application
ui <- fluidPage(
  sidebarLayout(
    sidebarPanel(
      textInput("name", "What is your name?", "Dean"),
      numericInput("num", "Number of flowers to show data for",
                   10, 1, nrow(iris))
    ),
    mainPanel(
      textOutput("greeting"),
      plotOutput("cars_plot"),
      tableOutput("iris_table")
    )
  )
)

# Define the server logic
server <- function(input, output) {
  # Create a plot of the "cars" dataset 
  output$cars_plot <- render___({
    plot(cars)
  })
  
  # Render a text greeting as "Hello <name>"
  output$greeting <- ___({
    paste("Hello", ___)
  })
  
  # Show a table of the first n rows of the "iris" data
  ___ <- ___({
    data <- iris[1:input$num, ]
    data
  })
}

# Run the application
shinyApp(ui = ui, server = server)
