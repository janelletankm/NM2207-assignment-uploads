



library(shiny)

# Define UI for app that draws a histogram ----
ui <- fluidPage(
  
  # App title ----
  titlePanel("Heavy Episodic Drinking - the Americas"),
  
  # Sidebar layout with input and output definitions ----
  sidebarLayout(
    
    # Sidebar panel for inputs ----
    sidebarPanel(
      
      # Input: Slider for the number of bins ----
      sliderInput(inputId = "bins",
                  label = "Number of bins:",
                  min = 1,
                  max = 50,
                  value = 30)
      
    ),
    
    # Main panel for displaying outputs ----
    mainPanel(
      
      # Output: Histogram ----
      plotOutput(outputId = "distPlot"),
      
      h2("Edits made:"),
      
      strong("This is a histogram of waiting times."),
      
      p("The command value = 30 is for setting a default value."),
      
      p(em("After editing the command in the R script, always remember to save it first before typing runApp(display.mode = 'showcase) in the console.
         Remember to stop all programmes before running it.")),
      
      p(code("This helps to display code in the output.")),
      
      p(div("Divisions are useful.")),
      
      div(HTML(
        "Hello <b>abc</b> <em>This is italic</em>
        <image><>"
      )),
      
      p("Note", span("span works similarly to div, but it works with groups of words instead.")),
      
      p("I inserted an image below for practice."),
      
      img(src = "flower-image.png", height = 400, width = 400)
      
    )
  )
)

# Define server logic required to draw a histogram ----
server <- function(input, output) {
  
  # Histogram of the Old Faithful Geyser Data ----
  # with requested number of bins
  # This expression that generates a histogram is wrapped in a call
  # to renderPlot to indicate that:
  #
  # 1. It is "reactive" and therefore should be automatically
  #    re-executed when inputs (input$bins) change
  # 2. Its output type is a plot
  output$distPlot <- renderPlot({
    
    x    <- faithful$waiting
    bins <- seq(min(x), max(x), length.out = input$bins + 1)
    
    hist(x, breaks = bins, col = "#75AADB", border = "white",
         xlab = "Waiting time to next eruption (in mins)",
         main = "Histogram of waiting times")
    
  })
  
}

# Create Shiny app ----
shinyApp(ui = ui, server = server)