# newtonRaphsonpython
def kousikka_pp13(g, x0, eps, delta, itermax):
    """
    Newton-Raphson method to determine the root of a function g(x)

    Inputs:
        g - function returning both g(x) and g'(x)
        x0 - initial guess
        eps - convergence threshold
        delta - divergence threshold
        itermax - maximum number of iterations

    Outputs:
        x - root approximation
    """

    xn = x0

    for n in range(itermax):
        f, fx = g(xn)
        xn1 = xn - f / fx

        if abs(xn1 - xn) < eps:
            return xn1

        if abs(xn1 - xn) > delta:
            raise ValueError('Divergence')

        xn = xn1

    raise ValueError('Maximum iterations exceeded')
