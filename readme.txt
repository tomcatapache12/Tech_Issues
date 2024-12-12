public class ExecutorServiceExample {

    public static void main(String[] args) throws Exception {
        // Example list to process
        List<Integer> numbers = generateNumbers(100); // Generate a list of 100 numbers

        // Number of threads
        int nThreads = 4;

        // Divide the list into sublists for each thread
        List<List<Integer>> partitions = partitionList(numbers, nThreads);

        // Create a list of CompletableFutures to handle the tasks
        List<CompletableFuture<Void>> futures = partitions.stream()
                .map(partition -> CompletableFuture.runAsync(() -> processList(partition))) // Submit tasks asynchronously
                .collect(Collectors.toList());

        // Wait for all tasks to complete and handle any exceptions
        try {
            // Wait for all tasks to complete
            CompletableFuture.allOf(futures.toArray(new CompletableFuture[0])).join(); 

        } catch (Exception e) {
            // If any exception occurs in any task, it will be propagated and we stop further execution
            throw new Exception("Task execution failed", e);
        }

        // If everything went fine, proceed with additional steps
        System.out.println("All tasks completed. Proceeding with additional steps...");
        additionalSteps();
    }
