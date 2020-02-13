public class ResizingArrayMaxPQ<Key extends Comparable<Key>> {
    private Key[] pq;
    private int N = 0;

    public MaxPQ(int maxN) {
        pq = (Key[]) new Comparable[maxN + 1];
    }

    // isEmpty and size method ignored

    public void insert(Key v) {
        if (N+1 == a.length) resize(2 * a.length);
        pq[++N] = v;
        swim(N);
    }

    public Key delMax() {
        Key max = pq[1];
        swap(1, N--);
        pq[N+1] = null;
        if (N > 0 && N == pq.length / 4) resize(a.length / 2);
        sink(1);
        return max;
    }

    // less and swap method ignored

    private void swim(int k) {
        while (k > 1 && less(k/2, k)) {
            swap(k/2, k);
            k = k/2;
        }
    }

    private void sink(int k) {
        while (2*k <= N) {
            int j = 2*k;
            if (j < N && less(j, j+1)) j++;
            if (!less(k, j)) break;
            swap(k, j);
            k = j;
        }
    }
}